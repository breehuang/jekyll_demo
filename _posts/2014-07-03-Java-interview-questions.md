---
layout: post
title: Java面试题整理
tag: Other
---

+ <p>运行时异常与一般异常有何异同？<br>
  异常表示程序运行过程中可能出现的非正常状态，运行时异常表示虚拟机的通常操作中可能遇到的异常，是一种常见运行错误。java编译器要求方法必须声明抛出可能发生的非运行时异常，但是并不要求必须声明抛出未被捕获的运行时异常。</p>


+ <p>说出Servlet的生命周期，并说出Servlet和CGI的区别。<br>
  Servlet被服务器实例化后，容器运行其init方法，请求到达时运行其service方法，service方法自动派遣运行与请求对应的doXXX方法（doGet，doPost）等，当服务器决定将实例销毁的时候调用其destroy方法。<br>
  与cgi的区别在于servlet处于服务器进程中，它通过多线程方式运行其service方法，一个实例可以服务于多个请求，并且其实例一般不会销毁，而CGI对每个请求都产生新的进程，服务完成后就销毁，所以效率上低于servlet。</p>


+ <p>Collection 和 Collections的区别。 <br>
  Collection是集合类的上级接口，继承与他的接口主要有Set 和List。<br>
  Collections是针对集合类的一个帮助类，他提供一系列静态方法实现对各种集合的搜索、排序、线程安全化等操作。</p>


+ <p>HashMap和Hashtable的区别。 <br>
  HashMap是Hashtable的轻量级实现（非线程安全的实现），他们都完成了Map接口，主要区别在于HashMap允许空（null）键值（key）,由于非线程安全，效率上可能高于Hashtable。<br>
  HashMap允许将null作为一个entry的key或者value，而Hashtable不允许。<br>
  HashMap把Hashtable的contains方法去掉了，改成containsvalue和containsKey。因为contains方法容易让人引起误解。<br>
  Hashtable继承自Dictionary类，而HashMap是Java1.2引进的Map interface的一个实现。<br>
  最大的不同是，Hashtable的方法是Synchronize的，而HashMap不是，在多个线程访问Hashtable时，不需要自己为它的方法实现同步，而HashMap 就必须为之提供外同步（如果是ArrayList：List lst = Collections.synchronizedList(new ArrayList());如果是HashMap：Map map = Collections.synchronizedMap(new HashMap());
  Hashtable和HashMap采用的hash/rehash算法都大概一样，所以性能不会有很大的差异。</p>


+ <p>final, finally, finalize的区别。<br> 
  final 用于声明属性，方法和类，分别表示属性不可变，方法不可覆盖，类不可继承。<br>
  finally是异常处理语句结构的一部分，表示总是执行。<br>
  finalize是Object类的一个方法，在垃圾收集器执行的时候会调用被回收对象的此方法，可以覆盖此方法提供垃圾收集时的其他资源回收，例如关闭文件等。</p>


+ <p>sleep() 和 wait() 有什么区别? <br>
  sleep是线程类（Thread）的方法，导致此线程暂停执行指定时间，给执行机会给其他线程，但是监控状态依然保持，到时后会自动恢复。调用sleep不会释放对象锁。<br>
  wait是Object类的方法，对此对象调用wait方法导致本线程放弃对象锁，进入等待此对象的等待锁定池，只有针对此对象发出notify方法（或notifyAll）后本线程才进入对象锁定池准备获得对象锁进入运行状态。</p>


+ <p>Overload和Override的区别。Overloaded的方法是否可以改变返回值的类型?<br>
  方法的重写Overriding和重载Overloading是Java多态性的不同表现。重写Overriding是父类与子类之间多态性的一种表现，重载Overloading是一个类中多态性的一种表现。如果在子类中定义某方法与其父类有相同的名称和参数，我们说该方法被重写 (Overriding)。子类的对象使用这个方法时，将调用子类中的定义，对它而言，父类中的定义如同被“屏蔽”了。如果在一个类中定义了多个同名的方法，它们或有不同的参数个数或有不同的参数类型，则称为方法的重载(Overloading)。Overloaded的方法是可以改变返回值的类型。</p>


+ <p>error和exception有什么区别?<br>
  error 表示恢复不是不可能但很困难的情况下的一种严重问题。比如说内存溢出。不可能指望程序能处理这样的情况。<br>
  exception 表示一种设计或实现问题。也就是说，它表示如果程序运行正常，从不会发生的情况。</p>


+ <p>同步和异步有何异同，在什么情况下分别使用他们？举例说明。<br>
  如果数据将在线程间共享。例如正在写的数据以后可能被另一个线程读到，或者正在读的数据可能已经被另一个线程写过了，那么这些数据就是共享数据，必须进行同步存取。<br>
  当应用程序在对象上调用了一个需要花费很长时间来执行的方法，并且不希望让程序等待方法的返回时，就应该使用异步编程，在很多情况下采用异步途径往往更有效率。</p>


+ <p>Static Nested Class 和 Inner Class的不同。 <br>
  Static Nested Class是被声明为静态（static）的内部类，它可以不依赖于外部类实例被实例化。而通常的内部类需要在外部类实例化后才能实例化。</p>


+ <p>什么时候用assert。 <br>
  assertion(断言)在软件开发中是一种常用的调试方式，很多开发语言中都支持这种机制。在实现中，assertion就是在程序中的一条语句，它对一个boolean表达式进行检查，一个正确程序必须保证这个boolean表达式的值为true；如果该值为false，说明程序已经处于不正确的状态下，系统将给出警告或退出。一般来说，assertion用于保证程序最基本、关键的正确性。assertion检查通常在开发和测试时开启。为了提高性能，在软件发布后，assertion检查通常是关闭的。</p>


+ <p>GC是什么? 为什么要有GC? <br>
  GC是垃圾收集的意思（Gabage Collection）,内存处理是编程人员容易出现问题的地方，忘记或者错误的内存回收会导致程序或系统的不稳定甚至崩溃，Java提供的GC功能可以自动监测对象是否超过作用域从而达到自动回收内存的目的，Java语言没有提供释放已分配内存的显示操作方法。</p>


+ <p>Math.round(11.5)等於多少? Math.round(-11.5)等於多少? <br>
  Math.round(11.5)==12<br>
  Math.round(-11.5)==-11<br>
  round方法返回与参数最接近的长整数，参数加1/2后求其floor.</p>


+ <p>Java有没有goto?<br>
  java中的保留字，现在没有在java中使用。</p>


+ <p>说出数据连接池的工作机制是什么?<br>
  J2EE服务器启动时会建立一定数量的池连接，并一直维持不少于此数目的池连接。客户端程序需要连接时，池驱动程序会返回一个未使用的池连接并将其表记为忙。如果当前没有空闲连接，池驱动程序就新建一定数量的连接，新建连接的数量有配置参数决定。当使用的池连接调用完成后，池驱动程序将此连接表记为空闲，其他调用就可以使用这个连接。</p>


+ <p>Java中的异常处理机制的简单原理和应用。<br>
  当JAVA程序违反了JAVA的语义规则时，JAVA虚拟机就会将发生的错误表示为一个异常。违反语义规则包括2种情况。一种是JAVA类库内置的语义检查。例如数组下标越界,会引发IndexOutOfBoundsException;访问null的对象时会引发NullPointerException。另一种情况就是JAVA允许程序员扩展这种语义检查，程序员可以创建自己的异常，并自由选择在何时用throw关键字引发异常。所有的异常都是java.lang.Thowable的子类。</p>


+ <p>垃圾回收的优点和原理。<br>
  Java语言中一个显著的特点就是引入了垃圾回收机制，使c++程序员最头疼的内存管理的问题迎刃而解，它使得Java程序员在编写程序的时候不再需要考虑内存管理。由于有个垃圾回收机制，Java中的对象不再有“作用域”的概念，只有对象的引用才有“作用域”。垃圾回收可以有效的防止内存泄露，有效的使用可以使用的内存。垃圾回收器通常是作为一个单独的低级别的线程运行，不可预知的情况下对内存堆中已经死亡的或者长时间没有使用的对象进行清楚和回收，程序员不能实时的调用垃圾回收器对某个对象或所有对象进行垃圾回收。</p>






