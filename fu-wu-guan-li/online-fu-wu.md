# online服务

## 介绍

服务：online

介绍：实时处理kafka topic中的原始数据将数据写入hive中

## 服务状态 {#-0}

命令：

```text
cd /opt/growing-ansible ## 在ansible服务器上运行
ansible -i inventories/project_name/hosts online -m shell -a "jps"
```

## online的启动与停止 {#online-0}

**启动**

切换至online服务器

```text
/apps/svr/online/bin/check.sh # 执行即可
```

关闭：

```text
/apps/svr/online/bin/stop-all.sh
```

检查：

```text
jps
```

## online的基本操作 {#online-1}

online是在线实时任务，会把原始数据存放在hive中，hive没有安装用的是spark，所有如果要看数据的话需要登陆spark

```text
cd /apps/svr/spark##切换至安装目录下
./bin/sql-spark --master local[2] ##进入hive中
use gio; ##切换至gio库
show tables; ## 查看所有表格
select * from page; ## 通常查询page和visit表
show partitions page; ## 每半小时区分，还需要查看visit和action表，这是原始数据的表，如果没有数据需要查看他。
Select * from page where time like ‘20180322%’;
```

