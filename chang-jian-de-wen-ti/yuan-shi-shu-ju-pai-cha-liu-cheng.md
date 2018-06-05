# 原始数据排查流程

> 主要用于那个指标没有数据需要查看原始数据中是否已经采集

## 查询浏览量

查询的表: hive.page

备注： 该表的浏览量会根据page\_id进行去重

## 查询指标数据

查询的表：hive.action 1、查看pg库的rules表 检查是否有对应的rule规则，以及定义的xpath等\(获取rule\_id需要看query-service的日志信息\)

2、查看online数据 web-pv mobile-pv web-action-tag mobile-action-tag 如果action表没有数据就是online出了问题

3、查看hive的action表 根据rule表里定义的p、ai等规则 然后查看action表是否有数据，并且对比两个数据是否一致。

> 需注意: join时需要action表的p字段，如果没有p字段则不会join

4、查看action\_tag表是否也有相同的数据 如果action\_tag表没有数据应该是圈选元素的值不一样导致，如果有数据对比两个数据是否一致。 注意：可以使用rule\_id和xpath进行查看过滤数据

5、查看full-join-pv表，是否有数据

6、查看full-join-tag表 注意：通过rule\_id 过滤数据

## 页面级变量数据

postgres 库：page\_level\_variables表 hive：page\_props 表

## 用户变量数据

> 用户变量的计算时间：一天计算一次

1、查看原始数据表： 根据ai+时间查看user\_props表中是否有原始数据，找到数据后查看是否有空值，并且注意数据的时间一定要在后台创建之后上传，否则不被计算。

2、查看pg库的people\_variables表 根据ai查看所有用户变量的上传信息，以及归因类型，如果是最终则会查找dynamic\_user\_props\_honor ，最近则会查找dynamic\_user\_props\_honor表（会在qs中输出）

3、查看是否被关联 user\_props\_day 的dim字段是否被关联可以根据cs1字段进行查询

4、查看hbase 的数据 查看最终归因表和最近归因表是否 最终归因表：dynamic\_user\_props\_honor 最近归因表：dimension\_honor\_day

> 注意： 最终归因修改为最近会中断数据 最近修改最终不会影响

