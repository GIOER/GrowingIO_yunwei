## id-service服务 {#id-service}

### 介绍

服务：id-service

介绍：根据访问的用户产生一个uid，用于判断多个设备是否是同一个用户

### 状态 {#-0}

打开marathon界面id-service在ucloud/bigdata下

status显示running就是运行状态

命令查看：
```
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f idservice_id ## 查看idservice的运行日志
```
### id-service的启动与关闭 {#id-service-0}

启动：

切换到/apps/svr/id-service 下执行`update.sh`即可
```
cd /apps/svr/id-service ; sh update.sh
```
关闭：

参考frontend

### id-service的基本操作 {#id-service-1}

参考frontend服务