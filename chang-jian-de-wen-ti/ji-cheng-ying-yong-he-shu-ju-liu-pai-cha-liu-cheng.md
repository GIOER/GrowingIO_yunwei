# 集成应用和数据流排查流程

在浏览器输入vds的域名➕status 是否返回works，如果返回即负载均衡正常

2.检查vds-api是否接受到数据

去 vds-api服务器，然后去/data/vds-api/events-log目录下查看文件是否有数据存在。

3.检查log2kafka是否有问题

去vds-api服务器，切入log2kafka的容器内，进入到logs目录下，查看sendlog是否有报错输出正常的情况应该是空的log文件，然后检查其他的日志文件是否有报错。

4.检查kafka是否获取原始数据

_切换至kafka服务器，在kafka的安装目录下/apps/svr执行看是否会实时的输出数据_

_bin/kafka-console-consumer.sh --zookeeper zookeeper:2181/kafka --from-beginning --topic topic \#\# topic根据不同应用进行选择_

1. 检查hive是否有原始数据

切换online服务器，切换至spark的安装目录/apps/svr/spark下，然后进入spark中，查看page和visit以及其他表是否有数据存在。

cd /apps/svr/spark/bin

./spark-sql --master local\[4\]

use gio;

select \* from page where time like ‘20180324%’; \#查看page、visit表,由于数据量比较大，最好使用count统计下

1. 检查hbase是否有数据

去offline服务器，切换到phoenix安装目录下，然后进入phoenix中，查看ai\_domain表是否有集成的那个应用的ai

cd /apps/svr/phoenix/bin

./start-sql.sh

select \* from ai\_domain; \#这个表记录的每个项目的ai

8．去页面检查

在页面进行检查应该就可以检查到应用了。

9．前提要检查所有服务的状态是否全部启动，是否启动有问题

