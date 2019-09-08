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
  
