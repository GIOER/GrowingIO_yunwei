## gateway服务 {#gateway}

### 介绍：

服务：gateway

介绍：主要是链接account／backend和frontend

### 状态： {#-0}

打开marathon界面gateway在ucloud/mid-end下,和frontend一样显示running状态代表正常


命令查看：

```
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f gateway_id ## 查看gatway的运行日志
```
### gateway的启动与关闭 {#gateway-0}

启动：

切换到/apps/svr/growing- gateway下执行`install.sh`即可
```
cd /apps/svr/growing- gateway &amp;&amp; sh install.sh
```
关闭：

参考frontend服务

### gateway的基本操作 {#gateway-1}

参考frontend服务