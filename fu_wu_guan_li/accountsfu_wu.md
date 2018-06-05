## accounts服务 {#accounts}

### 介绍

服务：accounts

介绍：主要是认证服务

### 状态 {#-0}

和frontend一样status显示running就是运行状态

命令查看：
```
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f account_id ## 查看accounts的运行日志
```
### accounts的启动与关闭 {#accounts-0}

启动：

切换到/apps/svr/growing- accounts下执行`install.sh`即可
```
cd /apps/svr/growing- accounts&amp;&amp; sh install.sh
```
关闭：

参考frontend

### accounts的基本操作 {#accounts-1}

参考frontend服务