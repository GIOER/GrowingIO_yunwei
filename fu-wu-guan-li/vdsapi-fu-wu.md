# vds-api服务

## 介绍

服务：vds-api（一般是两台）

介绍：后端数据收集上来存放的第一位置

## 状态 {#-0}

打开marathon界面vds-api在ucloud/bigdata下

status显示running就是运行状态

命令查看：

```text
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f vdsapi_id ## 查看vdsapi的运行日志
```

## vds-api的启动与关闭 {#vds-api-0}

启动：

切换到/apps/svr/vds-api/ 下执行`install.sh`即可

```text
cd /apps/svr/vds-api ; sh install.sh
```

关闭：

参考frontend

## vds-api的基本操作 {#vds-api-1}

参考frontend服务

