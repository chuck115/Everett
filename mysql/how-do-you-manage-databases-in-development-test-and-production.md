


更改表结构
=================


工具： pt-online-schema-change

命令：
$ pt-online-schema-change --alter "modify name varchar(20) not null default '' comment '物品名称'" --nocheck-replication-filters --recursion-method=processlist h=192.168.4.45,P=3316,u=mha_mgr,p=123456,D=test,t=zzzz --execute

h host
P port
u user
p password
D database
t table

注意事项：
1. 外部用双引号， 内部用单引号
2. 乱码问题， 加上 --charset=utf8mb4



更改数据
=================

begin;
更新语句
rollback;


查看更新的数据条数是否与预期一致
