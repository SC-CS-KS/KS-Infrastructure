# Redis生成ID
主要依赖于Redis是单线程的，所以也可以用生成全局唯一的ID
	可以用Redis的原子操作 INCR和INCRBY来实现
可以使用Redis集群来获取更高的吞吐量
比较适合使用Redis来生成每天从0开始的流水号
	比如订单号=日期+当日自增长号
		可以每天在Redis中生成一个Key，使用INCR进行累加

优点
	不依赖于数据库，灵活方便，且性能优于数据库
	数字ID天然排序，对分页或者需要排序的结果很有帮助
缺点
	如果系统中没有Redis，还需要引入新的组件，增加系统复杂度
	需要编码和配置的工作量比较大

    