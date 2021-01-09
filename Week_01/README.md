学习笔记

## 遇到过这样一个大内存对象的问题，未解
一个WEB应用使用mongoDB，存在对大集合做聚合操作（相当于insert）。
JAVA应用使用驱动里的MongoClient类作为数据库连接池，发现并发多或者数据量大时（同一时间段写入多）会产生老年代GC，MAT工具打开看是 PowerOfTwoBufferPool是最大的leak对象.
目前没有什么好的方案解决此问题，助教大大如果对此问题有兴趣可以进一步沟通，谢谢：

Mongo社区的提问，里面回答的人的连接需要梯子
https://mongoing.com/anspress/question/mongoclient-poweroftwobufferpool-leak-memory

网上类似问题，尝试过没有效果
https://www.coollf.com/archives/%E4%B8%80%E6%AC%A1%E5%8E%8B%E6%B5%8Boom%E9%97%AE%E9%A2%98%E7%9A%84%E6%8E%92%E6%9F%A5
