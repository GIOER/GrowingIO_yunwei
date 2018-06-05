# Offline服务

## 介绍

服务：offline

介绍：定时处理online写入hive中的原始数据，并且计算后写入hbase服务

## 服务状态 {#-0}

命令：

```text
cd /opt/growing-ansible ## 在ansible服务器上运行
ansible -i inventories/project_name/hosts offline -m shell -a "jps"
```

## 启动与停止 {#-1}

**启动**

切换至offline服务器

```text
/apps/svr/online/bin/check-server.sh # 启动server服务，主要作用是计算
/apps/svr/offline/bin/check-jobsubmitter.sh offline #启动offline服务，主要作用是提交任务
/apps/svr/offline/bin/check-jobsubmitter.sh load #启动load服务，主要作用是提交任务
```

关闭：

```text
/apps/svr/online/bin/kill-server.sh
/apps/svr/online/bin/kill-jobsubmitter.sh offline
/apps/svr/online/bin/kill-jobsubmitter.sh load
```

检查：

```text
jps
```

## offline基本操作 {#offline-0}

offline会定时去hive中取原始数据然后在yarn上计算最终写入hbase中，hbase和spark做了集成

```text
cd /apps/svr/phoneix/ ## 切换至phoneix安装目录，phoneix是一个集合插件
./bin/start-sqlline.sh ##进入hbase中
select * from ai_domain; ## 初次集成的时候如果后端数据上来并且kafka和hive没有问题这里就可以看到该项目的ai，然后去界面检测应该就可以检测到应用了，同时还有很多表new_user,metric_honor,es_honor等等等
```

offline目录

```text
cd /apps/svr/offline/ #offline安装目录
在安装目录下有main和load两个文件，这两个文件的主要作用是查看offline计算到那个时间点，一般offline是每一小时计算一次。
```

