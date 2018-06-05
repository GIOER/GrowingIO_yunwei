## Hbase集群 {#hbase}

### 介绍

服务：hbase（两主多从）

介绍：hbase集群

### 服务状态 {#-0}

命令：
```
cd /opt/growing-ansible ## 在ansible服务器上运行

ansible -i inventories/project_name/hosts hbase -m shell -a "jps"
```

### hbase的启动与停止 {#hbase-0}

**启动**

切换至ansible服务器执行
```
cd /opt/growing-ansible
ansible-playbook -i inventories/project_name/hosts tool-scripts/start-hbase.yml
```
关闭：

切换至ansible服务器执行
```
cd /opt/growing-ansible
ansible-playbook -i inventories/project_name/hosts tool-scripts/stop-hbase.yml
```
检查：

可以登陆hbase服务查看服务进程监听端口，也可以通过hbasemaster ip地址+60010查看hbase的管理界面，可以查看当前hbase的界面是否正常

### hbase基本操作 {#hbase-1}

参考hbase的官方文档