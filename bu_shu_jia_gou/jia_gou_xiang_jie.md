## 架构详解

本架构分为两个部分：

一：后端数据采集部分

二：前端访问部分

### 后端数据采集 {#-0}

1. 需要对需要分析的网站或者app进行sdk集成，主要用于数据采集。
2. 然后数据会通过marathon-lb服务将数据传输至vds-api服务\(前提是pg库里有该项目的ai\)
3. vds-api服务收到数据后，log2kafka异步的读取vds的数据并且根据id-service将数据发送给kafka。
4. kafka收到数据后会，online服务会实时的去kafka里取数据并且将数据写入hive表中（原始数据）。
5. hive表里有了原始数据后offline服务会定时的是hive表里取数据进行计算，然后将数据写入hbase中。

### 前端访问 {#-1}

1. 用户首先进入frontend服务，frontend是一个页面渲染服务。
2. 然后会通过gateway将请求跳转至account服务，gateway的作用就是链接各个服务，account就是一个认证服务。
3. 然后会讲请求的一些指标数据会将请求通过gateway分发至backend服务。
4. ackend服务会去chart-service里拿取数据。
5. chart-service也会去query-service拿取数据，而query-service会也会实时的去hbase请求数据



