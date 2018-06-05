# zookeeper集群

## 介绍

服务：zookeeper（一般是三台）

介绍：zookeeper集群

## 服务状态 {#-0}

命令：

```text
cd /opt/growing-ansible ## 在ansible服务器上运行
ansible -i inventories/project_name/hosts zookeeper -m shell -a 'lsof –I :2181'
```

## zookeeper启动与停止 {#zookeeper-0}

**启动：**

切换至ansible服务器执行

```text
cd /opt/growing-ansible
ansible-playbook -i inventories/project_name/hosts tool-scripts/start-zookeeper.yml
```

关闭：

切换至ansible服务器执行

```text
cd /opt/growing-ansible
ansible-playbook -i inventories/project_name/hosts tool-scripts/stop-zookeeper.yml
```

单机启动：

需要切换zookeeper服务器

```text
/apps/svr/zookeeper/bin/zkServer.sh start
```

