#ThreadLocal


###SDK文档
```
	Implements a thread-local storage, that is, a variable for which each thread has its own value. 
	All threads share the same ThreadLocal object, but each sees a different value when accessing it, and changes made by one thread do not affect the other threads. The implementation supports null values.
```

实现了一个本地线程存储，即一个变量对于每个线程都有其自己的值。  
所有线程共享一个ThreadLocal对象，但是访问时每个线程获取的值都不一样，并且一个改变一个线程的本地变量并不会影响其他线程本地变量的值。本地变量的值可以为null。


###源码结构
{% highlight java %}

public class ThreadLocal<T> {

	private static AtomicInteger hashCounter = new AtomicInteger(0);
	
	private final int hash = hashCounter.getAndAdd(0x61c88647 * 2);

	public ThreadLocal() {}
	
	public T get() {
					
	}
	
	public void set(T value) {
				
	}
	
	public void remove() {
						
	}
	
	protected T initialValue() {
		return null;
	}
	
	Values initializeValues(Thread current) {
		return current.localValues = new Values();
	}
	
	Values values(Thread current) {
		return current.localValues;
	}
	
	static class Values {
		
	}
}

{% endhighlight %}