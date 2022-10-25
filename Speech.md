# Speech

- [Speech](#speech)
  - [The Previous](#the-previous)
  - [Context](#context)
      - [code sample](#code-sample)
  - [Conclusion](#conclusion)
  - [Keyword](#keyword)

## The Previous

前情提要

Java Programming Language been using desktop app, micro device, service and so on. Most of users of the Java Programming language need to be able to write reliable multithreaded software and solve the multithreaded problem. An regular programmer must solving the problems. The pyramidal logical thread pools were created in software, how to make threads run faster and more efficient? That has happened a lot in their career.

This request should not be a dependency in maven project or module in java package. That is a util solution in Java Programming Languagem, like `java.lang.Thread`.

java语言被运用于多端平台。而Java语言的用户需要能编写多线程软件并解决多线程的问题。以我为例，一个普通程序员需要解决的问题。在程序内构建金字塔型逻辑的线程池后，如何优化？这一场景在我的职业生涯中大量发生。

这个需求并不应该作为maven工程的依赖或者java的一个module包。这是一个java语言的工具解决方案，正如`java.lang.Thread`。

## Context

正文

As it metioned before, we using `ThreadPoolExecutor` to solving multithreaded resource. But it has not solved the problem when we using multi pyramidal logical threadpools. At that situation, the threadpools will cause some resource wasted. Because, at the time of the thread were executed, maybe its child thread is not done or being waited.

What's worse, at the pyramidal threadpools' situation, `ThreadPoolExecutor` cannot solving the resources of container or system, which be reasonable using or spending in software. 

To solve this situation, we need to build a thread pool in jvm. Registing the relationship of threads, meanwhile, running the thread by using stacktrace(dependency relationship). User could be focus on the business of domain and the probable of resources(like CPU, memory, disk and I/O devices).

正如前文所述，当前大环境下线程池处理的使用场景。

更糟的是，当构建塔式线程池状态下，线程池工具并不能解决容器或系统的资源被线程有效在软件中使用的问题

为了解决这一现象，我们需要在jvm中构建线程池，对线程间关系做持有记录，同时基于堆栈进行运行（依赖关系）。用户可以专注于业务领域，以及大致的资源

#### code sample

```java

	private static final String SCHEDULE_THREAD_TYPE = "Schedule";
	private static final String REGULAR_THREAD_TYPE = "Regular";
	private static final ConcurrentHashMap<String, ExecutorService> PYRAMIDAL_THREAD_POOL = new ConcurrentHashMap<>();

    public ThreadHelperUtil getInstance() {
        return new ThreadHelperUtil();
    }

	public <T> Future<T> submit(String domainThreadName, Callable<T> caller, String type) {
		return submit(MIN_CORE_SIZE, MAX_CORE_SIZE, defaultHandler, domainThreadName, caller, type, Thread.NORM_PRIORITY);
	}
	
	public void submit(String domainThreadName, Runnable caller, String type) {
		submit(MIN_CORE_SIZE, MAX_CORE_SIZE, defaultHandler, domainThreadName, caller, type, Thread.NORM_PRIORITY);
	}

```


## Conclusion

结尾部分

Last and most, the solution of multithreaded pools in java programming language is a common request from java community.


## Keyword

关键词释义

* CPU polling
  * CPU轮询
* thread
  * 线程——结合CPU轮询时，线程所能感知的
* context
  * 上下文
