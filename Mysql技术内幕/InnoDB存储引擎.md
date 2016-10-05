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
```
for(int i=0; i< 10; i++) {
    do thing once per second;
    sleep 1 second;
}
do things once per ten seconds;
```
- 每秒一次的操作包括
1. 日志缓冲刷新到磁盘，即使这个事务还没有提交（总是）
2. 合并插入缓冲（可能）
3. 至多刷新100个Innodb的缓冲池中的脏页到磁盘（可能）
4. 如果当前没有用户活用，则切换到background loop（可能）

## InnoDB特性
- 插入缓冲
针对聚集索引，辅助索引 //TODO

- 两次写

- 自适应哈希索引

- 异步IO

- 刷新邻接页

