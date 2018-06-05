# charts-service服务

## 介绍

服务：charts-service

介绍：图显服务

## 状态

打开marathon界面charts-service在ucloud/mid-end下

status显示running就是运行状态

命令查看：

```text
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f charts_id ## 查看charts的运行日志
```

## charts-service的启动与关闭 {#charts-service-0}

启动：

切换到/apps/svr/charts-service下执行`install.sh`即可

```text
cd /apps/svr/charts-service ; sh install.sh
```

关闭：

参考frontend

## 基本操作

参考frontend服务

