# query-service服务

## 介绍

服务：query-service

介绍：后端数据查询服务

## 状态 {#-0}

打开marathon界面query-service在ucloud/bigdata下

status显示running就是运行状态

命令查看：

```text
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f query_id ## 查看query的运行日志
```

## query-service的启动与关闭 {#query-service-0}

启动：

切换到/apps/svr/query-service下执行install.sh即可

```text
cd /apps/svr/query-service ; sh install.sh
```

关闭：

参考frontend

## query-service的基本操作 {#query-service-1}

参考frontend服务

