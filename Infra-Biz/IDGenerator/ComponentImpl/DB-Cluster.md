# 基于数据库集群模式

数据库换成主从模式集群

设置起始值和自增步长
```sql
MySQL_1 配置:
	set @@auto_increment_offset = 1;     -- 起始值
	set @@auto_increment_increment = 2;  -- 步长

MySQL_2 配置:
	set @@auto_increment_offset = 2;     -- 起始值
	set @@auto_increment_increment = 2;  -- 步长
```

## 优点
解决DB单点问题

## 劣势
不利于后续扩容，而且实际上单个数据库自身压力还是大，依旧无法满足高并发场景。