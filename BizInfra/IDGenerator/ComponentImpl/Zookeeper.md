# Zookeeper 生成 ID

通过其znode数据版本来生成序列号
	可以生成32位和64位的数据版本号，客户端可以使用这个版本号来作为唯一的序列号

很少会使用zookeeper来生成唯一ID
	主要是由于需要依赖zookeeper，并且是多步调用API
	如果在竞争较大的情况下，需要考虑使用分布式锁
		因此，性能在高并发的分布式环境下，也不甚理想。

