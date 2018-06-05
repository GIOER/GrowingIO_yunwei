## kafka集群 {#kafka}

### 介绍

服务：kafka（一般是三台）

介绍：收集log2kafka传过来的数据，并且放到相对应的topic中

### 状态 {#-0}

命令：
```
cd /opt/growing-ansible ## 在ansbile服务器上运行

ansible -i inventories/project_name/hosts kafka -m shell -a "jps |grep -i kafka ";
```
### kafka的启动与关闭 {#kafka-0}

启动：
```
ansible-playbook -i inventories/project_name/hosts tool-scripts/start-kafka.yml # 启动所有kafka
```

关闭：
```
ansible-playbook -i inventories/project_name/hosts tool-scripts/stop-kafka.yml # 关闭所有kafka
```

单台启动：(需要去kafka服务本地启动)

```
/apps/svr/kafka/bin/kafka-server-start.sh -daemon /apps/svr/kafka/config/server.properties
```

单台关闭：

```
kill kafka-id 即可
```

### kafka的基本操作 {#kafka-1}

log2kfka会将采集上来的数据根据不通的topic传送至不同的topic中，kafka也会实时的接受数据

显示所有topic

切换至kafka服务器
```
cd /apps/svr/kafka
bin/kafka-topics.sh --zookeeper zookeeper:2181/kafka --list #指定zookeeper服务的主机名和端口
```

根据topic查看是否有数据显示
```
bin/kafka-console-consumer.sh --zookeeper zookeeper:2181/kafka --from-beginning --topic topic #写入需要查看的topic名称
```
因为是实时的如果有数据的话应该会实时的显示