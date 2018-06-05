## Hadoop服务 {#hadoop}

### 介绍

服务：Hadoop（两主多从）

介绍：hadoop集群

### Hadoop的启动与停止 {#hadoop-0}

**启动**

切换至ansible服务器执行
```
cd /opt/growing-ansible
ansible-playbook -i inventories/project_name/hosts tool-scripts/start-hdfs.yml
ansible-playbook -i inventories/project_name/hosts tool-scripts/start-yarn.yml
```

**关闭**

切换至ansible服务器执行
```
cd /opt/growing-ansible
ansible-playbook -i inventories/project_name/hosts tool-scripts/stop-hdfs.yml
ansible-playbook -i inventories/project_name/hosts tool-scripts/ stop-yarn.yml
```

**检查**

可以登陆hadoop服务查看服务进程监听端口，也可以访问hadoop master的50070端口检查集群是否启动，也可以检查当前存活的节点以及集群当前的情况

### Hadoop基本操作 {#hadoop-1}

可以参考hadoop的官方文档

yarn的介绍
在浏览器输入hadoop master的ip➕8088端口可以看到当前启动的所有任务（online+offline）根据online和offline启动的进程数不同，同时在第一行可以看到当前集群资源使用情况。