## postgres数据库 {#postgres}

### 介绍

服务：postgres

介绍：存放GIO系统的数据

### 服务状态 {#-0}

命令：

切换至postgres服务器
```
ps –ef|grep postgres 查看进程是否存在
```
### postgres启动地址 {#postgres-0}

**启动：**

切换至postgres服务器执行
```
systemctl start postgres-9.5
```
**关闭：**

切换至postgres服务器执行
```
systemctl stop postgres-9.5
```
### postgres基本操作 {#postgres-1}
```
psql -U apps -d growing ## 使用apps用户进入growing的数据库
```

#### 在界面添加角色等按钮，修改项目为商业版 {#-1}
```
insert into contracts(id,project_id,project_version_id,is_active,created_at,updated_at,start_date) values(3,5,3,'t','2017-12-12 00:00:07.767','2017-12-12 00:00:07.767','2016-10-14');

id： 设置新的id
project_id：找出需要关联的项目（projects表里有）
project_version_id：找出商业版的id信息（project_versions表里有）
is_active：是否激活，为t
created_at：创建时间，
updated_at：更新时间
start_date：开始时间
```
基本增删改查可以参考官网链接

#### 查看所有的项目 {#-2}
```
select name,keyid from projects;
```
#### 修改用户的密码 {#-3}

切换至growing_accounts库
```
\c growing_accounts
update accounts set password_digest='password' where id = '需要修改用户名的user_id';
```