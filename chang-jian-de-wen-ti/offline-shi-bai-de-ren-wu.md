# offline失败的任务

数据库： postgres

登陆方式：psql -U apps -d rules

查看rules的job\_todo表

统计当前所有任务的状态

```text
select clz, count(clz) from job_todo group by clz;
```

