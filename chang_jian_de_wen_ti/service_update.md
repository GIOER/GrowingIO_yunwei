##服务的升级
### 容器服务升级

##### 升级的大概步骤

1.  gio提供升级包的镜像
2.  将gio提供的景象load到需要升级服务的docker镜像中。
3.  打开marathon界面修改镜像名称的版本即可

```
导入docker images中
docker load -i package.tar.gz
查看镜像
docker ps
```
### 非容器的升级 {#-1}

##### 升级的大概步骤

1.  gio提供需要升级的jar包或者服务软件包
2.  将服务软件包拷贝至服务器
3.  替换之前的服务或者jar包
4.  重新启动