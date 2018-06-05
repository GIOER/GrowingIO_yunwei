## redis服务 {#redis}

### 介绍

服务：redis

介绍：缓存服务

### 状态： {#-0}

打开marathon界面就可以看到redis

status显示running就是运行状态

命令查看：
```
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f redis_id ## 查看redis的运行日志
```
### redis的启动与关闭 {#redis-0}

启动：

切换到/apps/svr/redis 下执行`install.sh`即可
```
cd /apps/svr/redis ; sh install.sh
```
关闭：

参考frontend

### redis的基本操作 {#redis-1}

#### 概览数据为0 {#0}

如果offline重新计算数据，数据已经计算完成（在单图中可以看到数据），可以删除redis的key清理redis的缓存
```
redis-cli keys '*qa29' | xargs redis-cli del
```
#### 在用户管理界面缺少添加角色的按钮 {#-1}

pg数据库确定修改好，然后删除redis的key才可以生效

```
keys role*  #删除
```
