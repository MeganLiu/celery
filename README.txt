# celery

Celery is a distributed task scheduling module which can be easily integrated with applications (in our case, python celery) and provide task scheduling options in a simple yet reliable manner.  Celery can be used to schedule consumer polls at regular intervals instead of running it forever, however things like graceful message consumption, offset management had to be tuned to make this work. 


kafka与celery的区别
kafka它们属于消息队列；celery它们属于任务队列。

消息队列和任务队列，最大的不同之处就在于理念的不同 -- 消息队列传递的是“消息”，任务队列传递的是“任务”。

 我们可以放到具体的应用场景上:

消息队列用来快速消费队列中的消息。比如日志处理场景，我们需要把不同服务器上的日志合并到一起，这时就需要用到消息队列。
任务队列是用来执行一个耗时任务。比如用户在购买的一件物品后，通常需要计算用户的积分以及等级，并把它们保存到数据库。这时就需要用到任务队列。

从上面的例子可看出:

消息队列更侧重于消息的吞吐、处理，具有有处理海量信息的能力。另外利用消息队列的生产者和消费者的概念，也可以实现任务队列的功能，但是还需要进行额外的开发。
任务队列则提供了执行任务所需的功能，比如任务的重试，结果的返回，任务状态记录等。虽然也有并发的处理能力，但一般不适用于高吞吐量快速消费的场景。
任务队列其实和远程函数调用差不多，但和thrift、grpc什么不同，它不需要定义描述文件，调用的方式也不是网络请求方式，而是利用消息队列传递任务信息。



