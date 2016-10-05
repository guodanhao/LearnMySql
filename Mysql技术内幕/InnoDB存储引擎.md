## 体系架构
一个大的内存池，多线程模型

## InnoDb体系结构
- Master Thread：将缓冲池中的数据异步刷新到磁盘中，保证数据的一致性，包括脏页的刷新，合并插入缓冲，UNDO页回收
- IO Thread
- Purge Thread
- Page Cleaner Thread

## 内存
1. 缓冲池
索引页、数据页、undo页、插入缓冲页、自适应哈希页、InnoDB存储的锁信息、数据字典信息
（Q:缓冲池所放的数据页有多大,不可能把整个数据的数据都放进去吧，那放的是什么？）


## CheckPoint技术

## Master Thread

## InnoDB特性
- 插入缓冲
针对聚集索引，辅助索引 //TODO

- 两次写

- 自适应哈希索引

- 异步IO

- 刷新邻接页

