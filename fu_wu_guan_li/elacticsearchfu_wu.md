## **elacticsearch**服务 {#elacticsearch}

### 介绍

服务：elasticsearch

介绍：文本搜索服务

### 状态 {#-0}

打开marathon界面elasticsearch在ucloud/bigdata下

status显示running就是运行状态

命令查看：
```
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f elasticsearch_id ## 查看elasticsearch的运行日志
```

### elasticsearch的启动与关闭 {#elasticsearch}

切换到/apps/svr/elasticsearch下执行`update.sh`即可
```
cd /apps/svr/elasticsearch ; sh update.sh
```
关闭：

参考frontend

### elasticsearch的基本操作 {#elasticsearch-0}

参考frontend服务