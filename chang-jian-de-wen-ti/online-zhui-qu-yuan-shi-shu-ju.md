# online追取原始数据

由于磁盘空间满了或者其他原因，导致online没有将原始数据读区至hive中，offline 没有统计出数。

操作：

登陆online服务器

```text
cd /apps/svr/spark/bin
./spark-sql --master local[4]
```

2、 切换到gio数据库。

```text
use gio; #切换至gio数据库
```

3、查看online原始数据，正常是每半小时会有一条记录

```text
show partitions action;
```

看显示的时间，如果缺少一段时间的数据，也就是online没有读取那段时间的原始数据，如缺少201803241600 – 201803242400，输出没有这个时间段。

4、停止online和offline服务

详情停止参考online和offline的服务停止命令（注意定时任务，先注释，数据追上以后删除注释）

5、修改online的配置文件

```text
cd /apps/svr/online/conf

vim common.conf
```

修改online读区数据配置kafka.reset,重启online.开始追原始数据.\(earliest/latest\)

```text
app.after: 1487203200000 从指定的时间节点读取kafka数据
action {

expire.hour: 24

} 这个配置，读取数据截止小时，即只读取最近24小时
```

追数完成后修改回默认配置，重启online

6、确定元数据是否正常获取

重复1、2、3操作查看是否有缺失时间短的数据

7、元数据已经OK，需要配置跑offline jobs 。

登陆offline服务器

```text
cd /apps/svr/offline
```

8、修改时间

将时间修改至缺失数据前的时间点然后修改MainFrame.pos 和 Load.pos文件，重启offline服务。

9、等待验证数据

