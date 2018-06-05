## 界面中没有添加角色的按钮

切换至数据库服务器
```
psql -U apps -d growing
insert into contracts(id,project_id,project_version_id,is_active,created_at,updated_at,start_date) values(3,5,3,'t','2017-12-12 00:00:07.767','2017-12-12 00:00:07.767','2016-10-14');

id： 设置新的id
project_id：找出需要关联的项目（projects表里有）
project_version_id：找出商业版的id信息（project_versions表里有）
is_active：是否激活，为t
created_at：创建时间，
updated_at：更新时间
start_date：开始时间
```