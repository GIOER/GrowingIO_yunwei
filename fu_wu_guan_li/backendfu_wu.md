## backend服务 {#backend}

### 介绍

服务：backend

介绍：后端数据展示的主服务

### 状态

打开marathon界面backend在ucloud/mid-end下

命令查看：

```
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f backend_id ## 查看backend的运行日志
```
### backend的启动与关闭 {#backend-0}

启动：

切换到/apps/svr/growing backend下执行`install.sh`即可
```
cd /apps/svr/growing-backend ; sh install.sh
```
关闭：

参考frontend

### backend基本操作 {#backend-1}

参考frontend服务