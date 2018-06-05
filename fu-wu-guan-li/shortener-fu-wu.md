# shortener服务

## 介绍

服务：shortener

介绍：短链服务，将长链接地址返回短连接地址，圈选app时需要扫描二维码，如果链接太长则无法识别，所有需要一个短链接服务转换下url地址。

## 状态 {#-0}

打开marathon界面shortener在ucloud/mid-end下

status显示running就是运行状态

命令查看：

```text
docker ps ## 可以查看当前运行的容器
docker logs --tail 100 -f shortener_id ## 查看shortener的运行日志
```

## shortener的启动与关闭 {#shortener-0}

启动：

切换到/apps/svr/growing-url-shortener下执行`install.sh`即可

```text
cd /apps/svr/growing-url-shortener ; sh install.sh
```

关闭：

参考frontend

## shortener的基本操作 {#shortener-1}

参考frontend服务

