---
layout: post
title:  "Dispatch Queue"
date:   2015-05-12 22:28:49
categories: iOS-core Dispatch Queue
---

# Dispatch Queue
 Grand Gentral Dispatch(GCD) 是异步执行任务的技术之一。开发者只需要定义想执行的任务追加到适当的Dispatch Queue中，GCD就能生成必要的线程并计划执行任务。
 {% highlight objective-C %}
	dispatch_async(queue, ^{
	        /*
	         * 要执行的任务
	         */
	});
 {% endhighlight %} 


 1. **The main queue**: 与主线程功能相同。main queue可以调用`dispatch_get_main_queue()`来获得。因为main queue是与主线程相关的，所以这是一个**串行队列**。
 2. **Global queues**: 全局队列是**并发队列**，并由整个进程共享。进程中存在三个全局队列：高、中（默认）、低三个优先级队列。可以调用`dispatch_get_global_queue`函数传入优先级来访问队列。
 3. **用户队列**: 用户队列 (GCD并没有一个特定的名字来形容这种队列，所以我们称其为用户队列) 是用函数 `dispatch_queue_create` 创建的队列. 
	 * **Serial Dispatch Queue**
		等待当前正在处理的任务完成后再执行下一个任务，每次只执行一个任务，按照顺序执行
	 * **Concurrent Dispatch Queue**
		不管当前的任务是否执行完毕都开始执行下一个任务，任务并发执行 ( 并行执行的处理数量取决于当前的系统的状态。系统只生成所需的线程执行处理，处理结束后，系统会结束不需要的线程。)

 {% highlight objective-C %}

//第一个参数为queue的名称,Apple建议我们使用倒置域名来命名队列
//第二个参数为Null 创建Serial dispatch queue; 如果为DISPATCH_QUEUE_CONCURRENT 则创建的是Concurrent queue;   
    //dispatch_queue_t mySerialQueue = dispatch_queue_create("org.itjoy.gcd.mySerialQueue", NULL);
    dispatch_queue_t mySerialQueue = dispatch_queue_create("org.itjoy.gcd.mySerialQueue", DISPATCH_QUEUE_SERIAL); // DISPATCH_QUEUE_SERIAL is default
    
    dispatch_async(mySerialQueue, ^{
        NSLog(@"hello GCD");
    });
    
    dispatch_release(mySerialQueue);  ////释放 对应的是retain

    
    dispatch_queue_t myConcurrentQueue = dispatch_queue_create("org.itjoy.gcd.myConcurrentQueue", DISPATCH_QUEUE_CONCURRENT);
    dispatch_async(myConcurrentQueue, ^{
        NSLog(@"heloo jin");
    });
    dispatch_release(myConcurrentQueue); ///释放 对应的是retain

 {% endhighlight %} 