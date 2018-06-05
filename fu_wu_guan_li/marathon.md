## marathon {#marathon}

### 介绍

描述：介绍所有的前中端服务，也就是将所有的服务统一放置marathon管理，方便对服务的启动、停止、修改配置参数等操作

### 操作 {#-0}

登陆marathon服务器，使用docker ps 检查marathon是否在运行状态

命令：

```
docker ps ## 检查marathon是否启动
docker logs --tail 100 -f marathon-id ## 检查marathon运行日志
netstat -ltunp |grep 8080 ## 检查marathon端口是否被监听
```

### 访问marathon {#marathon-0}

用一台可以访问marathon内网ip的电脑，输入ip+端口即可访问marathon界面

浏览器输入：

```
http://marathon_ip:8080
```

备注

确保可以ping通marathon服务器并且可以telnet通8080端口

### marathon的启动与关闭 {#marathon-1}

启动：

登陆marathon服务器，切换到/apps/svr目录下执行`install_marathon.sh`即可

```
cd /apps/svr && sh install_marathon.sh
```

关闭：

可以使用docker rm进行关闭marathon

```
docker rm marathon
```



### marathon的web界面 {#marathon-2}

![](/images/fuwuguanli/marathon_ui.png)



