# log2kafka服务

## 介绍

服务：log2kafka（一般是两台和vds成对出现）

介绍：会根据id-service服务返回的结果将数据传送至kafka服务

## 状态 {#-0}

打开marathon界面log2kafka在ucloud/bigdata下

status显示running就是运行状态

命令查看：

```text
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f log2kafka_id ## 查看log2kafka的运行日志
```

## log2kafka的启动与关闭 {#log2kafka-0}

启动：

切换到/apps/svr/log2kafka 下执行`update.sh`即可

```text
cd /apps/svr/log2kafka &amp;&amp; sh update.sh
```

关闭：

参考frontend

## log2kafka的基本操作 {#log2kafka-1}

参考frontend服务

