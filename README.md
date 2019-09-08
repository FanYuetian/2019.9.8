# 2019.9.8
牛客网知识补充

一.基础
  1.java中变量有两种
    基本数据类型（原始类型）：byte、short、char、int、long、float、double、boolean
    引用数据类型
  2.枚举类型是java5新增的特性，是一种新类型，允许用常量来表示特定的数据片段，而且全部以类型安全形式来表示，是特殊的类，可以拥有成员变量和方法
  3.system.out.println()方法
    3.1 system是java.lang里面的一个类
        java.lang.System
    3.2 out是system里面的一个静态数据成员,而且这个成员是java.io.PrintStream类的引用
        public final static PrintStream out = null;
    3.3 println()是java.io.PrintStream类中的一个方法
    3.4 system.out是"类名.成员名"=>system.out.println是实例引用调用方法
  4.java实现了真数组，避免覆盖数据的可能，而不是数据覆盖类型。真数组的总结：在内存中连续分配；数组所存在的内存空间为数组专用，避免了数据被覆盖问题；数组内存放的类型是确定的，唯一的。
  5.实现GBK编码字节流到UTF-8编码字节流的转换：
    byte[] src,dst;
    dst=new String(src,"GBK").getBytes("UTF-8")
  6.forward.jsp中有动作<jsp:forward page="index.htm"/>这时运行地址栏是forward.jsp;如果是重定向地址栏是index.html
  7.列表（list）元素有序、可重复；集合（set）元素无序、不可重复
  8.map使用键值对存放，可以一对多，key不重复，value可以重复
  9.重载的规则：（参数列表、同一类中）
    1>参数列表（顺序、个数、类型）必须不同
    2>可以有不同的返回类型、访问修饰符、异常
  10.重写的规则：（父子类）
     修饰符>=,返回值<=,同名,同参数列表,抛出异常<=
  11.jar 打包；javac 编译；javah生成c++头文档；javadoc生成解释API文档
  12.命令行运行java文件:javac hello.java=>java hello
  13.访问修饰符：public:类、包、不同包子类、不同包非子类
                protect：类、包、不同包子类
                default：类、包
                private：类
  14.getparameter():获取post/get传递的参数值
     getinitparameter():获取tomcat的server.xml中设置context的初始化参数
     getattribute():获取对象容器中的数据值
     getrequestdispatcher():请求转发
  15.super和this都只能位于构造器的第一行，而且不能同时使用，这是因为会造成初始化两次，this用于调用重载的构造方法，super用于调用父类被子类重写的方法
  16.abstract类只能用来派生子类，不能用来创建abstract类的对象
  17.java.lang.NumberFormatException:非纯数字的字符串转化为integer对象会报数字格式异常
  18.%和 * 是同一个优先级
  19.正向溢出：最小值+余数-1
     负向溢出：最大值-余数+1
     byte[-128,127]
     129>127为正向溢出：-128+(129%127)-1=-127
     -129为负向溢出:结果为127-(-129%-128)+1=127
  20.static不能修饰局部变量
  21.JVM中，是使用监视器锁来实现不同线程的异步执行，在语法上的表现就是synchronized
  22.-n=~n+1
  23.wait()和notify/notifyAll()是放在同步代码块中的，因此线程在执行它们时，肯定是进入了临界区中的，该线程肯定获得了锁；当线程执行wait()时，会把当前锁释放，然后让出CPU，进入等待状态；当执行notify/notifyAll方法时，会唤醒一个处于等待该 对象锁 的线程，然后继续往下执行，直到执行完退出对象锁的区域后再释放锁
