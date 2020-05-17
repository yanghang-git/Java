# JVM与Java体系结构

​	**Jvm的模型**

  					 <img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587910862809.png" alt="1587910862809" style="zoom:67%;" />

​		大部分的Java开发人员，除了在项目中使用到与Java平台相关的各种高精尖技术，对于Java技术的核心Java虚拟节了解甚少。

**语言在电脑上解析的流程**

​								<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587912034692.png" alt="1587912034692" style="zoom:80%;" />

​		计算机系统体系对我们来说越来越远，在不了解底层实现方式的前提下，通过高级语言很容易编写程序代码。但事实上计算机并不认识高级语言

**Java VS C++**

​														<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587912789566.png" alt="1587912789566" style="zoom: 50%;"/> 

​		垃圾收集机制为我们打理了很多繁琐的工作，大大提高了开发的效率，但是，垃圾收集也不是万能的，懂得JVM内部的内存结构、工作机制，是设计高扩展性应用和诊断运行时问题的基础,也是Java.工程师进阶的必备能力。

**JVM官方数据下载路径**

​	 https://docs.oracle.com/javase/specs/index.html 

**Java生态圈**

​		Java是目前应用最为广泛的软件开发平台之一。随着Java以及Java社区的不断壮大，Java也早已不再是简简单单的一门计算机语言了，它更是一个平台、一种文化、一个社区。

- <strong>作为一个平台</strong>、Java虚拟机扮演着举足轻重的作用。
  - Groovy、 Scala、 JRuby、 Kotlin等都是Java平台的一部分
- <strong>作为一种文化</strong>，Java几乎成为了“开源” 的代名词。
  - 第三方开源软件和框架。如Tomcat、Struts, MyBatis， Spring等。
  - 就连JDK和JVM自身也有不少开源的实现，如OpenJDK、Harmony。
- <strong>作为一个社区</strong>，Java拥有全世界最多的技术拥护者和开源社区支持，有数不清的
  论坛和资料。从桌面应用软件、嵌入式开发到企业级应用、后台服务器、中间件,
  都可以看到Java的身影。其应用形式之复杂、参与人数之众多也令人昨舌。

**Java 跨平台的语言**

​		

​		<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587916071205.png" alt="1587916071205" style="zoom:70%;" /> 

​													“write once, run anywhere”

**JVM 跨语言的平台**

​		<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587916726132.png" alt="1587916726132" style="zoom:67%;" /> 

​		随着Java7的正式发布，Java 虚拟机的设计者们通过JSR-292规范基本实现在<strong>Java虛拟机平台.上运行非Java语言编写的程序。</strong>

​		Java,虚拟机根本不关心运行在其内部的程序到底是使用何种编程语言编写的，<strong>它只关心“字节码”文件</strong>。也就是说Java虚拟机拥有语言无关性，并不会单纯地与Java语言“终身绑定”，只要其他编程语言的编译结果满足并包含Java虛拟机的内部指令集、符号表以及其他的辅助信息，它就是一个有效的字节码文件，就能够被虛拟机所识别并装载运行。

​													<strong><em>Java不是最强大的语言，但是JVM是最强大的虚拟机</em></strong>

##### 虚拟机的描述

```官方解释
	The Java Virtual Machine is the cornerstone of the Java platform. It is the component of thetechnology responsible for its hardware- and operating system-independence, the small size of itscompiled code, and its ability to protect users from malicious programs.
```
​		Java虚拟机是Java平台的基石。它是技术的组成部分，负责其硬件和操作系统的独立性，其编译代码的小尺寸，以及保护用户免受恶意程序攻击的能力。

**字节码**

​		我们平时说的java字节码指的是用j ava语言编译成的字节码。准确的说任何能在jvm平台上执行的字节码格式都是一样的。所以应该统称为:**jvm字节码**。

​		不同的编译器，可以编译出相同的字节码文件，字节码文件也可以在不同的JVM上运行。

​		Java虚拟机与Java 语言并没有必然的联系，它只与特定的二进制文件格式一Class文件格式所关联， Class 文件中包含了Java 虚拟机指令集(或者称为字节码、Bytecodes)和符号表，还有一些其他辅助信息。

**多语言混合编程**

​		**Java平台上的多语言混合编程正成为主流，通过特定领域的语言去解决特定领域的问题是当前软件开发应对日趋复杂的项目需求的一个方向**。

​		试想一下，在一个项目之中，并行处理用Clojure语言编写，展示层使用JRuby/Rails，中间层则是Java,每个应用层都将使用不同的编程语言来完成，而且，接口对每一层的开发者都是透明的，**各种语言之间的交互不存在任何困难，就像使用自己语言的原生API一样方便，因为它们最终都运行在一个虚拟机之上**。

对这些运行于Java虚拟机之上、Java之外的语言，来自系统级的、底层的支持正在迅速增强，以JSR-292 为核心的一系列项目和功能改进(如DaVinci Machine项目 、Nashorn引擎、 InvokeDynamic指令、java. lang. invoke包等)，**推动pava虚拟机从“Java语言的虚拟机”向多语言虚拟机”的方向发展**。

##### Java发展的重大事件

​		1990年，在Sun计算机公司中，由Patrick Naughton、MikeSheridan及James Gosling 领导的小组Green Team, 开发出的新的程序语言，命名为Oak,后期命名为Java

​		1995年，Sun正式发布Java和HotJava产品，Java首次公开亮相。.

​		1996年1月23日Sun Microsystems发布了JDK 1.0.

​		1998年，JDK 1.2版本发布。同时，Sun发布了JSP/Servlet、 EJB规范，以及将Java分成了J2EE、 J2SE和J2ME。这表明 了Java开始向 企业、桌面应用和移动设备应用3大领域挺进。

​		2000年，JDK 1.3发布，**Java HotSpot Virtual Machine正式发布，成为Java的默认虛拟机**。

​		2002年，JDK 1. 4发布，古老的Classic虛拟机退出历史舞台。

​		2003年年底，**Java平 台的Scala正式发布，同年Groovy也加入了Java阵营**。

​		2004年，JDK 1.5发布。同时JDK 1. 5改名为JavaSE 5.0。

​		2006年，JDK 6发布。同年，**Java开源并建立了OpenJDK**。 顺理成章，**Hotspot虚拟机也成为了OpenJDK中 的默认虚拟机**。

​		2007年，**Java平台迎来了新伙伴Clojure**。

​		2008年，Oracle收购了BEA, **得到了JRockit 虚拟机**。

​		2009年，Twitter宣 布把后台大部分程序从Ruby迁移到Scala，这是Java平台的又一次大规模应用。

​		2010年，Oracle收购 了Sun,**获得Java商标和最具价值的HotSpot虛拟机**。此时，Oracle拥有市场占用率最高的两款虚拟机HotSpot和JRockit，并计划在术来对它们进行整合: HotRockit. JCP组织管理: Java语言

​		2011年，JDK7发布。在JDK 1. 7u4中，**正式启用了新的垃圾回收器G1**。

​		2017年，JDK9发 布。**将G1设置为默认GC，替代CMS**。同年，**IBM的J9开源**，形成了现在的Open J9社区

​		2018年，Android的Java侵权案判决，Goog1e赔偿Oracle计88亿美元
​			同年，Oracle宣告JavaEE成为历史名词，JDBC、JMS、Servlet赠予Eclipse基金会
​			同年，JDK11发布，LTS版本的JDK,**发布革命性的ZGC,调整JDK授权许可**

​		2019年，JDK12发布，加入RedHat领导开发的**Shenandoah GC**

**Open JDK 和 Oracle JDK**

​		![1587953777593](C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587953777593.png)

在JDK11之前，OracleJDK中还会存在- -些OpenJDK中没有的、闭源的功能。但在JDK11中，我们可以认为0penJDK和OracleJDK代码实质上已经""完全"一致的程度。

##### 虚拟机与Java虚拟机

**虚拟机**

​		所谓虚拟机(Virtual Machine)，就是一台虚拟的计算机。它是一款软件，用来执行一系列虚拟计算机指令。大体上，虚拟机可以分为系统虚拟机和程序虚拟机。
​			大名鼎鼎的Visual Box， VMware就属于系统虚拟机，它们完全是对物理计算机的仿真，提供了一个可运行	完整操作系统的软件平台。
​			程序虚拟机的典型代表就是Java虚拟机，它专门为执行单个计算机程序而设计，在Java虚拟机中执行的指令	我们称为Java字节码指令。

​	无论是系统虚拟机还是程序虚拟机，在上面运行的软件都被限制于虛拟机提供的资源中。

**Java虚拟机**

​		Java虛拟机是一台执行Java字节码的虚拟计算机，它拥有独立的运行机制，其运行的Java字节码也未必由Java语言编译而成。

​		JVM平台的各种语言可以共享Java虚拟机带来的跨平台性、优秀的垃圾回器，以及可靠的即时编译器。

​		Java技术的核心就是Java虚拟机(JVM，Java Virtual Machine) ,因为所有的Java程序都运行在Java虚拟机内部。

​		**作用**

​				Java虚拟机就是二进制字节码的运行环境，负责装载字节码到其内部，解释/编译为对应平台上的机器指令执行。每一条JRva指令，Java虚拟机规范中都有详细定义，如怎么取操作数，怎么处理操作数，处理结果放在哪里。

​		**特点**

​				一次编译，到处运行
​				自动内存管理
​				自动垃圾 回收功能

##### JVM的整体结构

​						<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587955486099.png" alt="1587955486099" style="zoom:80%;" /> 

​		HotSpot VM是目前市面.上高性能虚拟机的代表作之一。

​		它采用解释器与即时编译器并存的架构。

​		在今天，Java程序的运行性能早已脱胎换骨，已经达到了可以和C/C++程序一较高下的地步。

##### JVM的架构模型

​		Java编译器输入的指令流基本上是一种基于栈的指令集架构，另外一种指令集架构则是基于寄存器的指令集架构。

​		具体来说:这两种架构之间的区别:
​				基于栈式架构的特点
​						设计和实现更简单，适用于资源受限的系统;
​						避开了寄存器的分配难题:使用零地址指令方式分配。
​						指令流中的指令大部分是零地址指令，其执行过程依赖于操作栈。指令集更小,编译器容易实现。
​						不需要硬件支持，可移植性更好，更好实现跨平台

​				基于寄存器架构的特点
​						典型的应用是x8 6的二进制指令集:比如传统的Pc以及Android的Davlik虛拟机。
​						指令集架构则完全依赖硬件，可移植性差
​						性能优秀和执行更高效;
​						花费更少的指令去完成一项操作。
​						在大部分情况下，基于寄存器架构的指令集往往都以一地址指令、二地址指令和三地址指令为主，				而基于栈式架构的指令集却是以零地址指令为主。

​		**总结**

​		由于跨平台性的设计，Java的指令都是根据栈来设计的。不同平台CPU架构不同，所以不能设计为基于寄存器的。优点是跨平台， 指令集小，编译器容易实现，缺点是性能下降，实现同样的功能需要更多的指令。

​		时至今日，尽管嵌入式平台已经不是Java程序的主流运行平台了(准确来说应该是HotSpotVM的宿主环境已经不局限于嵌入式平台了)。

​	栈：	跨平台性、指令集小、指令多;执行性能比寄存器差

##### JVM的生命周期

​	**虚拟机的启动**

​			Java虚拟机的启动是通过引导类加载器(bootstrap class loader) 创建一个初始类(initial class) 来完成的，	这个类是由虚拟机的具体实现指定的。	

​	**虚拟机的执行**

​			一个运行中的Java虚拟机有着一个清晰的任务:执行Java程序。
​			程序开始执行时他才运行，程序结束时他就停止。
​			执行一个所谓的Java程序的时候，真真正正在执行的是一个叫做Java虚拟机的进程。			

​	**虚拟机的退出**	

​			程序正常执行结束
​			程序在执行过程中遇到了异常或错误而异常终
​			由于操作系统出现错误而导致Java虚拟机进程终正
​			某线程调用Runt ime类或System类的exit方法，或Runtime类的halt方法，并且Java安全管理器也允许这次	exi t或halt操作。
​			除此之外，JNI ( Java Native Interface) 规范描述了用JNI Invocation APT 来加载或卸载JTava 虑拟机时，	       	Java 虑拟机的很出情况。

##### JVM发展历程

​	**Sun Classsic VM**

​			早在1996年Java1.0版本的时候，Sun公司发布了一款名为Sun Classic VM的Java虚拟机，它同时也是世界.	上第一款商用Java虚拟机，JDK1. 4时完全被淘汰。
​			这款虛拟机内部只提供解释器。
​			如果使用JIT编译器，就需要进行外挂。但是一-旦使用了JIT编译器，JIT就会接管虚拟机的执行系统。解释器	就不再工作。解释器和编译器不能配合工作。
​			现在hotspot内置了此虚拟机。

​	**Exact VM**

​			为了解决上一个虚拟机问题，jdk1. 2时，sun提供了此虛拟机。
​			Exact Memory Management:准确式内存管理
​				也可以叫Non-Conservative/Accurate Memory Management
​				虚拟机可以知道内存中某个位置的数据具体是什么类型。
​			具备现代高性能虚拟机的雏形
​				热点探测
​				编译器与解释器混合工作模式
​			只在Solaris平台短暂使用，其他平台上还是classic vm
​				英雄气短，终被Hotspot虚拟机替换

​	***SUN公司的HotSpot VM**

​		HotSpot历史
​			最初由一家名为“Longview Technologies"的小公司设计
​			1997年，此公司被Sun收购;2009年，Sun公司被甲骨文收购。
​			JDK1.3时，HotSpot VM成为默认虚拟机
​		目前Hotspot占有绝对的市场地位，称霸武林。
​			不管是现在仍在广泛使用的JDK6，还是使用比例较多的JDK8中，默认的虛拟机都是HotSpot
​			Sun/Oracle JDK和OpenJDK的默认虚拟机
​			因此本课程中默认介绍的虚拟机都是HotSpot，相关机制也主要是指HotSpot的GC机制。(比如其他两个商用虛拟机都没有方法区的概念)
​		从服务器、桌面到移动端、嵌入式都有应用。.
​		名称中的HotSpot指的就是它的热点代码探测技术。
​			通过计数器找到最具编译价值代码，触发即时编译或栈上替换
​			通过编译器与解释器协同工作，在最优化的程序响应时间与最佳执行性能中取得平衡

​	***BEA的JRockit**
​		专注于服务器端应用
​			它可以不太关注程序 启动速度，因此JRockit 内部不包含 解析器实现，全部代码都靠即时编译器编译后执行。
​		大量的行业基准测试显示，JRockit JVM是 世界上最快的JVM。
​			使用JRockit产品，客户已经体验到了显著的性能提高(一些超过了70号)和硬件成本的减少(达50号) 。
​		优势:全面的Java运行时解决方案组合
​			Rocki t面向延迟敏感型应用的解决方案JRockit Real Time提供以毫秒或微秒级的JVM响应时间，适合财务、军事指挥、电信网络的需要
​			MissionControl服务套件，它是一组以极低的开销来监控、管理和分析生产环境中的应用程序的工具。
​		2008年，BEA被Oracle收购。
​		Oracle表达了整合两大优秀虚拟机的工作，大致在JDK 8中完成。整合的方式是在HotSpot的基础，上，移植JRocki t的优秀特性。
​		高斯林:目前就职于谷歌，研究人工智能和水下机器人

​	***IBM的J9**

​		全称: IBM Technology for Java Virtual Machine， 简称IT4J，内部代号: J9
​		市场定位与HotSpot接近，服务器端、桌面应用、嵌入式等多用途VM
​		广泛用于IBM的各种Java产品。
​		目前，有影响力的三大商用服务器之一，也号称是世界上最快的Java虚拟机。
​		2017年左右，IBM发布 了开源J9 VM，命名为openJ9，交给Eclipse基金会管理，也称为Ecilpse openJ9

# 类加载子系统

​	**详细图**

<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587966623329.png" alt="1587966623329"  />

##### 类加载子系统作用

​	类加载器子系统负责从文件系统或者网络中加载Class文件，class文件在文件开头有特定的文件标识。
​	ClassLoader只负责class文件的加载，至于它是否可以运行，则由ExecutionEngine决定。
​	加载的类信息存放于一块称为方法区的内存空间。除了类的信息外，方法区中还会存放运行时常量池信息，可能还包括字符串字面量和数字常量(这部分常量信息是Class文件中常量池部分的内存映射)

**类加载器ClassLoader角色**

​							<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587968409073.png" alt="1587968409073" style="zoom:80%;" />  

1. classFile存在于本地硬盘上，可以理解为设计师画在纸上的模板，而最终这个模板在执行的时候是要加载到JVM当中来根据这个文件实例化出n个一模一样的实例。
2. class file加载到JVM中,被称为DNA元数据模板,放在方法区。
3. 在.class文件 --> JVM --> 最终成为元数据模板,此过程就要一个运输工具(类装载器Class Loader) ,扮演一个快递员的角色。

##### 类的加载过程

​		**图形**

<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587969080646.png" alt="1587969080646" style="zoom:80%;" />

<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587974654239.png" alt="1587974654239" style="zoom:80%;" />

###### 	加载

​		1. 通过一个类的全限定名获取定义此类的二进制字节流

​		2. 将这个字节流所代表的静态存储结构转化为方法区的运行时数据结构

​		3. *在内存中生成一个代表这 个类的java. lang. Class对象*，作为方法区这个类的各种数据的访问入口

​		**补充: 加载.class文件的方式**

​			从本地系统中直接加载
​			通过网络获取，典型场景: web Applet
​			从zip压缩包中读取，成为日后jar、war格式的基础
​			运行时计算生成，使用最多的是:动态代理技术
​			由其他文件生成，典型场景: JSP应用
​			从专有数据库中提取. class文件,比较少见
​			从加密文件中获取，典型的防Class文件被反编译的保护措施

###### 链接

​	**验证(Verify)** :

​		目的在于确保Class文件的字节流中包含信息符合当前虚拟机要求，保证被加载类的正确性，不会危害虚拟机自身安全。
​		主要包括四种验证，文件格式验证，元数据验证，字节码验证，符号引用验证。

​	**准备(Prepare)** :

​		为类变量分配内存并且设置该类变量的默认初始值，即零值。
​		*这里不包含用final修饰的static,因为final在编译的时候就会分配了，准备阶段会显式初始化*;
​		*这里不会为实例变量分配初始化*，类变量会在方法区中，而实例变量是会随着对象一起分配到Java堆中。

​	**解析(Resolve)** :
​		将常量池内的符号引用转换为直接引用的过程。
​		事实上，解析操作往往会伴随着JVM在执行完初始化之后再执行。
​		符号引用就是一组符号来描述所引用的目标。符号引用的字面量形式明确定义在《java 虚拟机规范》的Class文件格式中。直接引用就是直接指向目标的指针、相对偏移量或一个间接定位到目标的句柄。
​		解析动作主要针对类或接口、字段、类方法、接口方法、方法类型等。对应常量池中的CONSTANT Class info、 CONSTANT Fieldref info、 CONSTANT Methodref info等

###### 初始化

​	*初始化阶段就是执行类构造器方法<clinit> ()的过程*。
​	此方法不需定义，是javac编译 器自动收集类中的所有类变量的赋值动作和静态代码块中的语句合并而来。
​	构造器方法中指令按语句在源文件中出现的顺序执行。
​	*<clinit> ()不同于类的构造器*。(关联: 构造器是虚拟机视角下的<init>())
​	若该类具有父类，JVM会保证子类的<clinit>()执行前，父类的<clinit>()已经执行完毕。
​	虚拟机必须保证一个类的<clinit> ()方法在多线程下被同步加锁。

##### 类加载器的分类

​	JVM支持两种类型的类加载器，分别为**引导类加载器( BootstrapClassLoader)**和**自定义类加载器(User-Defined ClassLoader)** 。
​	从概念上来讲，自定义类加载器一般指的是程序中由开发人员自定义的一类类加载器，但是Java虚拟机规范却没有这么定义，而是**将所有派生于抽象类ClassLoader的类加载器都划分为自定义类加载器**。
​	无论类加载器的类型如何划分，在程序中我们最常见的类加载器始终只有3个。

​					<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587976298902.png" alt="1587976298902" style="zoom:67%;" />

​						***这里的四者关系时包含关系、不是上层下层、也不是子父类的继承关系。***

​	测试类加载器的关系。

```Java
public class ClassLoaderDemo {
    public static void main(String[] args) {
        // 获取系统类加载器        
        ClassLoader loader = ClassLoader.getSystemClassLoader();        				
        System.out.println(loader); // sun.misc.Launcher$AppClassLoader@18b4aac2        		// 通过系统类加载器获取其上层加载器: 扩展类加载器
        ClassLoader extLoader = loader.getParent();
        System.out.println(extLoader); // sun.misc.Launcher$ExtClassLoader@1540e19d        		   // 通过扩展类加载获取其上层加载器: 引导类加载器
        ClassLoader bootstrapLoader = extLoader.getParent();        
        System.out.println(bootstrapLoader); // null
        // 对于用户自定义类来说: 默认使用系统类加载器进行加载
        ClassLoader classLoader = ClassLoaderDemo.class.getClassLoader();
        System.out.println(classLoader); // sun.misc.Launcher$AppClassLoader@18b4aac2
        // String类使用 引导类加载器进行加载 ---> Java的核心类库都是使用引导类加载器进行加载的。
        ClassLoader stringLoader = String.class.getClassLoader();
        System.out.println(stringLoader); // null
    }
}
```

###### 虚拟机自带的加载器

​	**启动类加载器(引导类加载器, Bootstrap ClassLoader)**

​		这个类加载使用**C/C++**语言实现的，嵌套在JVM内部。
​		它用来加载Java的核心库(JAVA_ HOME/jre/lib/rt. jar、resources. jar或sun . boot. class.path路径下的内容) ,用于提供JVM自身需要的类
​		并不继承自java. lang. ClassLoader,没有父加载器。
​		加载扩展类和应用程序类加载器，并指定为他们的父类加载器。
​		出于安全考虑，Bootstrap启动类加载器只加载包名为java、javax、sun等开头的类。

​	**扩展类加载器(Extension ClassLoader)**
​		Java语言编写，由sun . misc. Launcher$ExtClassLoader实现。
​		派生于ClassLoader类
​		父类加载器为启动类加载器
​		从java.ext.dirs系统属性所指定的目录中加载类库，或从JDK的安装目录的jre/lib/ext子目录(扩展目录)下加载类库。如果用户创建的JAR放在此目录下，也会自动由扩展类加载器加载。

​	**应用程序类加载器(系统类加载器，AppClassLoader)**
​		java语 言编写，由sun .misc. Launcher$AppClassLoader实现
​		派生于ClassLoader类
​		父类加载器为扩展类加载器;
​		它负责加载环境变量classpath或系统属性java. class.path指定路径下的类库
​		该类加载是程序中默认的类加载器，一般来说，Java应用的类都是由它来完成加载
​		通过ClassLoader#getSystemClassLoader ()方法可以获取到该类加载器

##### 用户自定义类加载器

​	在Java的日常应用程序开发中，类的加载方式几乎是有上述3种类的加载器相互配合执行的，在必要时，我们还可以自定义类加载器，来指定类的加载方式。

​	**为什么要自定义类加载器?**

​		隔离加载类
​		修改类加载的方式
​		扩展加载源
​		防止源码泄漏

​	**用户自定义类如载器实现步骤**:
​		1. 开发人员可以通过继承抽象类java. lang . ClassLoader类的方式，实现自己的类加载器，以满足一些特殊的需求。
​		2. 在JDK1.2之前，在自定义类加载器时，总会去继承ClassLoader类并重写loadClass()方法，从而实现自定义的类加载类，但是在JDK1.2之后已不再建议用户去覆盖loadClass()方法，而是建议把自定义的类加载逻辑写在findClass ()方法中
​		3. 在编写自定义类加载器时，如果没有太过于复杂的需求，可以直接继承URLClassLoader类，这样就可以避免自己去编写findClass()方法及其获取字节码流的方式，使自定义类加载器编写更加简洁。

```Java
public class CustomClassLoader extends ClassLoader {
    @Override    
    protected Class<?> findClass(String name) throws ClassNotFoundException {
        System.out.println(name); // One        
        try {
            byte[] result = getClassFromCustomPath(name);
            if(result == null) {
                throw new FileNotFoundException();
            } else {
                return defineClass(name,  result, 0, result.length);
            }
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
        throw new ClassNotFoundException(name);
    }
    private byte[] getClassFromCustomPath(String name) {
        // 自定义路径中加载指定类: 细节略
        // 如果指定路径的字节码文件进行了加密，则需要在此方法中进行解密操作。
        return null;
    }
    public static void main(String[] args) {
        CustomClassLoader custom = new CustomClassLoader();
        try { 
            Class clazz = Class.forName("One", true , custom);  
            Object obj = clazz.newInstance();     
            System.out.println(obj.getClass().getClassLoader());  
        } catch (Exception e) {       
            e.printStackTrace(); 
        }  
    }
}
```

##### 关于ClassLoader

​	ClassLoader类，它是一个抽象类，其后所有的类加载器都集成自ClassLoader(不包括Bootstrap ClassLoader 启动类加载器)。

| 方法名称                                              | 描述                                                         |
| :---------------------------------------------------- | :----------------------------------------------------------- |
| getParent()                                           | 返回该类加载器的超类加载器。                                 |
| loadClass(String name)                                | 加载名称为name的类，返回结果为java.lang.Class类的实例        |
| findClass(String name)                                | 查找名称为name的类，返回结果为java.lang.Class类的实例        |
| findLoadedClass(String name)                          | 查找名称为name的已经加载过的类，返回结果为java.lang.Class类的实例 |
| defineClass(String name, byte[] b, int off , int len) | 把字节数组b中的内容转换为一个Java类，返回结果为Java.lang.Class类的实例。 |
| resolveClass(Class<?> c>                              | 连接指定的一个Java类。                                       |

​							<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587980769376.png" alt="1587980769376" style="zoom:80%;" />

​									sun.misc.Launcher它是一个java虚拟机的入口应用。

**获取ClassLoader的途径**

| 方法                                           | 描述                            |
| :--------------------------------------------- | ------------------------------- |
| Class.instance.getClassLoader()                | 获取当前类的ClassLoader         |
| Thread.currentThread().getContextClassLoader() | 获取当前线程上下文的ClassLoader |
| ClassLoader.getSystemClassLoader()             | 获取系统的ClassLoader           |
| DriverManager.getCallerClassLoader()           | 获取调用者的ClassLoader         |

##### 双亲委派机制

​	Java,虚拟机对class文件采用的是**按需加载**的方式，也就是说当需要使用该类时才会将它的class文件加载到内存生成class对象。而且加载某个类的class文件时，Java虛拟机采用的是双亲委派模式，即把请求交由父类处理，它是一种任务委派模式。

​	**工作原理**

​								<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587981788382.png" alt="1587981788382" style="zoom:80%;" />

​		1. 如果一个类加载器收到了类加载请求，它并不会自己先去加载，而是把这个请求委托给父类的加载器去执行;
​		2. 如果父类加载器还存在其父类加载器，则进一步向上委托，依次递归请求最终将到达顶层的启动类加载器
​		3. 如果父类加载器可以完成类加载任务，就成功返回，倘若父类加载器无法完成此加载任务，子加载器才会
尝试自己去加载，这就是双亲委派模式。

​	**优势**

​		避免类的重复加载
​		保护程序安全，防止核心API被随意篡改

###### 沙箱安全机制

​	自定义String类，但是在加载自定义String类的时候会率先使用引导类加载器加载，而引导类加载器在加载的程中会先加载jdk自带的文件(rt. jar包中java\lang\String.class)，报错信息说没有main方法，就是因为加载的是rt. jar包中的String类。这样可以保证对java核心源代码的保护，这就是沙箱安全机制。

​	**其他**

​		在JVM中表示两个class对象是否为同一个类存在两个必要条件:  																		      			类的完整类名必须一致，包括包名。																													        			加载这个类的ClassLoader (指ClassLoader实例对象)必须相同。

​		换句话说，在JVM中，即使这两个类对象(class对象)来源同-一个Class文件，被同一个虚拟机所加载，但只要加载它们的ClassLoader实例对象不同，那么这两个类对象也是不相等的。

------

​		JVM必须知道--个类型是由启动加载器加载的还是由用户类加载器加载的。如果一个类型是由用户类加载器加载的，那么JVM会**将这个类加载器的一个引用作为类型信息的一部分保存在方法区中**。当解析一个类型到另一个类型的引用的时候，JVM需 要保证这两个类型的类加载器是相同的。

------

​	Java程序对类的使用方式分为:**主动使用和被动使用**。
​		主动使用，又分为七种情况:
​			创建类的实例
​			访问某个类或接口的静态变量，或者对该静态变量赋值
​			调用类的静态方法
​			反射(比如: Class. forName)
​			初始化一个类的子类
​			Java虛拟机启动时被标明为启动类的类
​			JDK 7开始提供的动态语言支持:
​				java. lang. invoke . MethodHandle实例的解析结果
​				REF getStatic、 REF putStatic、 REF invokeStatic句柄对应的类没有初始化，则初始化
​		除了以上七种情况，其他使用Java类的方式都被看作是对**类的被动使用**, 都**不会导致类的初始化**。

# 运行时数据区概述及线程

​		**图解**

<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587984500091.png" alt="1587984500091" style="zoom:70%;" />

<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587984814456.png" alt="1587984814456" style="zoom: 80%;" />

​		Java虛拟机定义了若干种程序运行期间会使用到的运行时数据区，其中有一些会随着虚拟机启动而创建，随着虚拟机退出而销毁。另外一些则是与线程一一对应的，这些与线程对应的数据区域会随着线程开始和结束而创建和销毁。	灰色的为单独线程私有的，红色的为多个线程共享的。																					    		每个线程:独立包括程序计数器、栈、本地栈。
​		线程间共享:堆、堆外内存(永久代或元空间、代码缓存)					

 **详细**

​	<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587984884698.png" alt="1587984884698" style="zoom:70%;" />

​		内存是非常重要的系统资源，是硬盘和CPU的中间仓库及桥梁,承载着操作系统和应用程序的实时运行。JVM内存布局规定了Java在行过程中内存申请、分配、管理的策略，保证了JVM的高效稳定运行不同的JVM对于内存的划分方式和管理机制存在着部分差异。

​		每个JVM只有-一个Runt ime实例。即为运行时环境，相当于内存结构的中间的那个框框:运行时环境。

##### 线程

​	线程是-一个程序里的运行单元。JVM允许-一个应用有多个线程并行的执行。
​	在Hotspot JVM里， 每个线程都与操作系统的本地线程直接映射。
​		当一个Java线程准备好执行以后，此时一个操作系统的本地线程也同时创建。Java线程执行终止后，本地线程也会回收。
​	操作系统负责所有线程的安排调度到任何一个可用的CPU上。一旦本地线程初始化成功，它就会调用Java线程中的run ()方法。

​	如果你使用j console或者是任何-一个调试工具，都能看到在后台有许多线程在运行。这些后台线程不包括调用public static void main (String[])的main线程以及所有这个main线程自己创建的线程。这些主要的后台系统线程在Hotspot JVM里主要是以下几个:
​		虚拟机线程:这种线程的操作是需要JVM达到安全点才会出现。这些操作必须在不同的线程中发生的原因是他们都需要JVM达到安全点，这样堆才不会变化。这种线程的执行类型包括”stop-the-world"的垃圾收集，线程栈收集，线程挂起以及偏向锁撤销。
​		周期任务线程 :这种线程是时间周期事件的体现(比如中断)，他们一-般用于 周期性操作的调度执行。
​		GC线程:这种线程对在JVM里不同种类的垃圾收集行为提供了支持。
​		编译线程:这种线程在运行时会将字节码编译成到本地代码。
​		信号调度线程:这种线程接收信号并发送给JVM，在它内部通过调用适当的方法进行处理。

# 程序计数器(PC寄存器)

​	**PC Register介绍**

​		JVM中的程序计数寄存器(Program Counter Register) 中，Register的命名源于CPU的寄存器，寄存器存储指令相关的现场信息。CPU只有把数据装载到寄存器才能够运行。
​	这里，并非是广义上所指的物理寄存器，或许将其翻译为PC计数器(或指令计数器)会更加贴切(也称为程序钩子)，并且也不容易引起--些不必要的误会。JVM中的PC寄存器是对物理PC寄存器的一种抽象模拟。

​	它是一块很小的内存空间，几乎可以忽略不记。也是运行速度最快的存储区域。
​	在JVM规范中，每个线程都有它自己的程序计数器，是线程私有的，生命周期与线程的生命周期保持一致。
​	任何时间一个线程都只有一个方法在执行，也就是所谓的当前方法。程序计数器会存储当前线程正在执行的Java方法的JVM指令地址;或者，如果是在执行native方法，则是未指定值(undefined)。

​	它是程序控制流的指示器，分支、循环、跳转、异常处理、线程恢复等基础功能都需要依赖这个计数器来完成。
​	字节码解释器工作时就是通过改变这个计数器的值来选取下--条需要执行的字节码指令。
​	它是唯一一个 在Java虚拟机规范中没有规定任何OutOtMemoryError情况的区域。

​	**作用**

​									<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587987512231.png" alt="1587987512231" style="zoom:67%;" />

​		PC寄存器用来存储指向下一条指令的地址,也即将要执行的指令代码。由执行引擎读取下一条指令。

​		<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587988400180.png" alt="1587988400180" style="zoom:67%;" />		

# 虚拟机栈

##### 虚拟机栈概述

```摘自官方
Each Java Virtual Machine thread has a private Java Virtual Machine stack, created at the same time as the thread. A Java Virtual Machine stack stores frames (S2.6). A Java VirtualMachine stack is analogous to the stack of a conventional language such as C: it holds local variables and partial results, and plays a part in method invocation and retum. Because theJava Virtual Machine stack is never manipulated directly except to push and pop frames, frames may be heap allocated. The memory for a Java Virtual Machine stack does not need tobe contiguous.

In the First Edition of The Java Virtual Machine Specification, the Java Vitual Machine stack was known as the Java stack.

This specification permits Java Virtual Machine stacks either to be of a fixed size or to dynamically expand and contract as required by the computation. If the Java Virtual Machinestacks are of a fixed size, the size of each Java Virtual Machine stack may be chosen independently when that stack is created.

A Java Virtual Machine implementation may provide the programmer or the user control over the initial size of Java Virtual Machine stacks, as well as, in the case of dynamicallyexpanding or contracting Java Virtual Machine stacks, control over the maximum and minimum sizes.

The following exceptional conditions are associated with Java Virtual Machine stacks:

●	If the computation in a thread requires a larger Java Virtual Machine stack than is permitted, the Java Virtual Machine throws a StackOver flowError.

●	If Java Virtual Machine stacks can be dynamically expanded, and expansion is attempted but insufficient memory can be made available to effect the expansion, or if 
insufficient memory can be made available to create the initial Java Virtual Machine stack for a new thread, the Java Virtual Machine throws an OutOfMemoryErr or.
```

**虚拟栈出现的背景**

​	由于跨平台性的设计，Java的指令都是根据栈来设计的。不同平台CPU架构不同，所以不能设计为基于寄存器的。
​	优点是跨平台，指令集小，编译器容易实现，缺点是性能下降，实现同样的功能需要更多的指令。

**内存中的栈与堆**

​	栈是运行时的单位，而堆是存储的单位。
​		即:栈解决程序的运行问题，即程序如何执行，或者说如何处理数据。堆解决的是数据存储的问题，即数据怎么放、放在哪儿。

​	**虚拟机栈基本内容**

​	Java虚拟机栈是什么？

​		Java虚拟机栈(Java Virtual Machine Stack) ，早期也叫Java栈。每个线程在创建时都会创建--个虛拟机栈，其内部保存一个个的栈帧(Stack Frame) ，对应着一次次的Java方法调用。
​			是线程私有的

​	生命周期

​		声明周期与线程一致。

​	作用

​		主管Java程序的运行，它保存方法的局部变量(8种基本数据类型、对象的引用地址)、部分结果，并参与发给发的调用和返回。

​	 **栈的特点(优点)**

​		栈是一种快速有效的分配存储方式，访问速度仅次于程序计数器。
​		JVM直接对Java栈的操作只有两个:
​			每个方法执行，伴随着进栈(入栈、压栈)
​			执行结束后的出栈工作
​		对于栈来说不存在垃圾回收问题
​			GC ;  StackOverflowError

​	**栈中可能出现的异常**

​		Java 虚拟机规范允许Java栈的大小是动态的或者是固定不变的。
​			如果采用固定大小的Java虚拟机栈，那每一个线程的Java虚拟机栈容量可以在线程创建的时候独立选定。如果线程请求分配的栈容量超过Java虚拟机栈允许的最大容量，Java虚拟机将会抛出一个StackOverflowError异常。
​			如果Java虛拟机栈可以动态扩展，并且在尝试扩展的时候无法申请到足够的内存，或者在创建新的线程时没有足够的内存去创建对应的虚拟机栈，那Java虚拟机将会抛出一个OutOfMemoryError 异常。	

​	**设置栈内存大小**

​		我们可以使用参数 -Xss 选项来设置线程的最大栈空间，栈的大小直接绝对了函数调用的最大可达深度。

​		idea为例: Run -> Edit Configurations... -> Application -> 需要设置的类文件 -> VM options -> 输入设置 如 -Xss1024k

##### 栈的存储单位

​	**栈中存储什么?**

​		每个线程都有自己的栈，栈中的数据都是以栈帧(Stack Frame)的格式存在。
​		在这个线程上正在执行的每个方法都各自对应一个栈帧(StackFrame)。
​		栈帧是一个内存区块，是一个数据集，维系着方法执行过程中的各种数据信息。

​	**栈运行原理**

​					<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1587997330010.png" alt="1587997330010" style="zoom: 67%;" />

​		 JVM直接对Java栈的操作只有两个，就是对栈帧的压栈和出栈，遵循“先进后出”/“后进先出”原则。

​		在一条活动线程中， 一个时间点上，只会有一个活动的栈帧。即只有当前正在执行的方法的栈帧(栈顶栈帧)是有效的，这个栈帧被称为当前栈帧(Current Frame) ，与当前栈帧相对应的方法就是当前方法(CurrentMethod)，定义这个方法的类就是当前类(Current Class)

​		执行引擎运行的所有字节码指令只针对当前栈帧进行操作。

​		如果在该方法中调用了其他方法，对应的新的栈帧会被创建出来，放在栈的顶端，成为新的当前帧。

​		不同线程中所包含的栈帧是不允许存在相互引用的，即不可能在一个栈帧之中引用另外一个线程的栈帧。

​		如果当前方法调用了其他方法，方法返回之际，当前栈帧会传回此方法的执行结果给前一个栈帧，接着，虚拟机会丢弃当前栈帧，使得前一个栈帧重新成为当前栈帧。

​		Java方法有两种返回函数的方式，一种是正常的函数返回，使用return指令;另外一种是抛出异常。不管使用哪种方式，都会导致栈帧被弹出。

​	**栈帧的内部结构**

​	每个栈帧中存储着:																																							   		局部变量表(Local variables)
​		操作数栈(operand stack) ( 或表达式栈)
​		动态链接(Dynamic Linking) (或指 向运行时常量池的方法引用)
​		方法返回地址(ReturnAddress)(或方法正常退出或者异常退出的定义)
​		一些附加信息

###### 局部变量表( local variables)

​	局部变量表也被称之为局部变量数组或本地变量表

​	**定义为一个数字数组，主要用于存储方法参数和定义在方法体内的局部变量**,这些数据类型包括各类基本数据类型、对象引用(reference) ，以及returnAddress类型。

​	由于局部变量表是建立在线程的栈上，是线程的私有数据，因此**不存在数据安全问题**

​	**局部变量表所需的容量大小是在编译期确定下来的**，并保存在方法的Code属性的maximum local variables数据项中。在方法运行期间是不会改变局部变量表的大小的。

​	**方法嵌套调用的次数由栈的大小决定**。一般来说，**栈越大，方法嵌套调用次数越多**。对一个函数而言，它的参数和局部变量越多，使得局部变量表膨胀,它的栈帧就越大，以满足方法调用所需传递的信息增大的需求。进而函数调用就会占用更多的栈空间，导致其嵌套调用次数就会减少。

​	**局部变量表中的变量只在当前方法调用中有效**。在方法执行时，虚拟机通过使用局部变量表完成参数值到参数变量列表的传递过程。**当方法调用结束后，随着方法栈帧的销毁，局部变量表也会随之销毁**。

​	**Slot**

​		参数值的存放总是在局部变量数组的index0开始，到数组长度-1的索引结束。

​		局部变量表，最基本的存储单元是Slot (变量槽)

​		局部变量表中存放编译期可知的各种基本数据类型(8种)，引用类型(reference)，returnAddress类 型的变量。
​		在局部变量表里，**32位以内的类型只占用一个slot (包括returnAddress类型)，64位的类型(long和double)占用两个slot**。
​			byte、short 、char在存储前被转换为int，boolean 也被转换为int，0表示false，非0表示true。
​			long 和double 则占据两个Slot。

​													<img src="C:\Users\北方\AppData\Roaming\Typora\typora-user-images\1588122912164.png" alt="1588122912164" style="zoom:80%;" />

​		JVM会为局部变量表中的每一个Slot都分配一个访问索引，通过这个索引即可成功访问到局部变量表中指定的局部变量值

​		当一个实例方法被调用的时候，它的方法参数和方法体内部定义的局部变量将会**按照顺序被复制**到局部变量表中的每一个slot上

​		**如果需要访问局部变量表中一个64bit的局部变量值时，只需要使用前一个索引即可**。(比
如:访问long或double类型变量)

​		如果当前帧是由构造方法或者实例方法创建的, .那么**该对象引用this将会存放在index为0的
slot处**，其余的参数按照参数表顺序继续排列。

​	**重复利用**

​		**栈帧中的局部变量表中的槽位是可以重用的**，如果一个局部变量过了其作用域，那么在其作用域之后申明的新的局部变量就很有可能会复用过期局部变量的槽位，从而**达到节省资源的目的**。

​	**补充说明**

​		在栈帧中，与性能调优关系最为密切的部分就是前面提到的局部变量表。在方法执行时，虚拟机使用局部变量表完成方法的传递。

​		**局部变量表中的变量也是重要的垃圾回收根节点，只要被局部变量表中直接或间接引用的对象都不会被回收**。

###### 操作数栈(Operand Stack)

​	每一个独立的栈帧中除了包含局部变量表以外，还包含一个**后进先出**(Last-In-First-0ut)的操作数栈，也可以称之为**表达式栈**(Expression Stack) 。

​	**操作数栈，在方法执行过程中，根据字节码指令，往栈中写入数据或提取数据，即入栈(push) /出栈(pop)**。
​		某些字节码指令将值压入操作数栈，其余的字节码指令将操作数取出栈。使用它们后再把结果压入栈。
​		比如: 执行复制、交换、求和等操作

​	操作数栈，**主要用于保存计算过程的中间结果，同时作为计算过程中变量临时的存储空间**。

​	操作数栈就是JVM执行引擎的一个工作区，当一个方法刚开始执行的时候，一个新的栈帧也会随之被创建出来，**这个方法的操作数栈是空的**。

​	每一个操作数栈都会拥有一个明确的栈深度用于存储数值，其所需的最大深度在编译期就定义好了，保存在方法的Code属性中，为max_ stack的值。

​	栈中的任何一个元素都是可以任意的Java数据类型。
​		32bit的类型占用一个栈单位深度
​		64bit的类型 占用两个栈单位深度

​	操作数栈**并非采用访问索引的方式来进行数据访问**的，而是只能通过标准的入栈(push)和出栈(pop)操作来完成一次数据访问。

​	**如果被调用的方法带有返回值的话，其返回值将会被压入当前栈帧的操作数栈中**，并更新PC寄存器中下一条需要执行的字节码指令。

​	操作数栈中元素的数据类型必须与字节码指令的序列严格匹配，这由编译器在编译器期间进行验证，同时在类加载过程中的类检验阶段的数据流分析阶段要再次验证。

​	另外，我们说Java虚拟机的**解释引擎是基于栈的执行引擎**，其中的栈指的就是操作数栈。

**栈顶缓存技术**

​	基于栈式架构的虛拟机所使用的零地址指令更加紧凑，但完成一项操作的时候必然需要使用更多的入栈和出栈指令，这同时也就意味着将需要更多的指令分派( instruction dispatch)次数和内存读/写次数。

​	由于操作数是存储在内存中的，因此频繁地执行内存读/写操作必然会影响执行速度。为了解决这个问题，HotSpot JVM的设计者们提出了栈顶缓存(ToS，Top-of-Stack Cashing) 技术，**将栈顶元素全部缓存在物理CPU的寄存器中，以此降低对内存的读/写次数，提升执行引擎的执行效率**。

###### 动态链接(或指向运行时常量池的方法引用)

​	每一个栈帧内部都包含一个指向**运行时常量池中该栈帧所属方法的引用**。包含这个引用的目的就是为了支持当前方法的代码能够实现**动态链接(Dynamic Linking)** 。比如: invokedynamic指 令|

​	在Java源文件被编译到字节码文件中时，所有的变量和方法引用都作为符号引用(Symbolic Reference) 保存在class文件的常量池里。比如:描述-一个方法调用了另外的其他方法时，就是通过常量池中指向方法的符号引用来表示的，那么**动态链接的作用就是为了将这些符号引用转换为调用方法的直接引用**。

###### 方法的调用

​	在JVM中，将符号引用转换为调用方法的直接引用与方法的绑定机制相关。

​	**静态链接**:
​		当一个字节码文件被装载进JVM内部时，如果被调用的**目标方法在编译期可知**，且运行期保持不变时。这种情况下将调用方法的符号引用转换为直接引用的过程称之为静态链接。

​	**动态链接**:
​		如果**被调用的方法在编译期无法被确定下来**，也就是说，只能够在程序运行期将调用方法的符号引用转换为直接引用，由于这种引用转换过程具备动态性，因此也就被称之为动态链接。

​	对应的方法的绑定机制为: 早期绑定(Early Binding)和晚期绑定(Late Binding) 。**绑定是一个字段、方法或者类在符号引用被替换为直接引用的过程，这仅仅发生一次**。

​	**早期绑定**:
​		早期绑定就是指被调用的**目标方法如果在编译期可知，且运行期保持不变时**，即可将这个方法与所属的类型进行绑定，这样一来，由于明确了被调用的目标方法究竟是哪-一个，因此也就可以使用静态链接的方式将符号引用转换为直接引用。

​	**晚期绑定**:
​		如果**被调用的方法在编译期无法被确定下来，只能够在程序运行期根据实际的类型绑定相关的方法**，这种绑定方式也就被称之为晚期绑定。

​	随着高级语言的横空出世，类似于Java一样的基于面向对象的编程语言如今越来越多，尽管这类编程语言在语法风格上存在一定的差别，但是它们彼此之间始终保持着一个共性，那就是都支持封装、继承和多态等面向对象特性，既然**这一类的编程语言具备多态特性，那么自然也就具备早期绑定和晚期绑定两种绑定方式**。

​	Java中任何一个普通的方法其实都具备虛函数的特征，它们相当于C++语言中的虛函数(C++中则需要使用关键字virtual来显式定义)。如果在Java程序中不希望某个方法拥有虚函数的特征时，则可以使用关键字final来标记这个方法。

**非虚方法/虚方法**

​	如果方法在编译期就确定了具体的调用版本，这个版本在运行时是不可变的。这样的方法称为**非虚方法**。

​	静态方法、私有方法、final方法、 实例构造器、父类方法都是非虚方法。

​	其他方法称为虚方法。

​	虚拟机中提供了以下几条方法调用指令:

​		普通调用指令 :
​			**invokestatic:调用静态方法,解析阶段确定唯一方法版本**
​			**invokespecial:调用<init>方法、私有及父类方法，解析阶段确定唯一方法版本**
​			invokevirtual:调用所有虛方法
​			invokeinterface:调用接口方法

​		动态调用指令:
​			invokedynamic:动态解析出需要调用的方法，然后执行

​		普通指令固化在虚拟机内部，方法的调用执行不可人为干预，而invokedynamic指 令则支持由用户确定方法版本。其中**invokestatic指令和invokespecial指令调用的方法称为非虛方法，其余的( final修饰的除外)称为虚方法**。

​	**关于invokedynamic指令**

​		JVM字节码指令集- -直比较稳定，一直到Java7中才增加了一个.invokedynamic指令，这是J**ava为了实现「动态类型语言」支持而做的一种改进**。

​		但是在Java7中并没有提供直接生成invokedynamic指令的方法，需要借助ASM这种底层字节码工具来产生invokedynamic指令。**直到Java8的Lambda :表达式的出现，invokedynami c指令的生成，在Java中才有了直接的生成方式**。

​	Java7中增加的动态语言类型支持的本质是对Java虚拟机规范的修改，而不是对Java语言规则的修改，这- -块相对来讲比较复杂，增加了虚拟机中的方法调用，最直接的受益者就是运行在Java平台的动态语言的编译器。	

 **方法重写的本质**

​	**Java语言中方法重写的本质**:
​		找到操作数栈顶的第-一个元素所执行的对象的实际类型，记作}C.
​		如果在过程结束;如果不通类型C中找到与常量中的描述符合简单名称都相符的方法,则进行访问权限校验，如果通过则返回这个方法的直接引用，查找过，则返java. lang. IllegalAccessError异常。
​		否则，按照继承关系从下往.上依次对C的各个父类进行第2步的搜索和验证过程。
​		如果始终没有找到合适的方法，则抛出java. lang . AbstractMethodError异常。

​	**IllegalAccessError介绍**:
​		程序试图访问或修改一个属性或调用-一个方法，这个属性或方法，你没有权限访问。一般的，这个会引起编译器异常。这个错误如果发生在运行时，就说明一一个类发生了不兼容的改变。

​	**虚方法表**

​		在面向对象的编程中，会很频繁的使用到动态分派，如果在每次动态分派的过程中都要重新在类的方法元数据中搜索合适的目标的话就可能影响到执行效率。因此，**为了提高性能**，JVM采用在类的方法区建立一个虛方法表**(virtual method table) (非虛方法不会出现在表中)来实现。使用索引表来代替查找**。

​	每个类中都有一个虚方法表，表中存放着各个方法的实际入口。

​	那么虚方法表什么时候被创建?
​		虚方法表会在类加载的链接阶段被创建并开始初始化，类的变量初始值准备完成之后，JVM会把该类的方法表也初始化完毕。

###### 方法返回地址(Return Address)

​	存放调用该方法的pc寄存器的值。

​	一个方法的结束，有两种方式:
​		正常执行完成
​		出现未处理的异常，非正常退出

​	无论通过哪种方式退出，在方法退出后都返回到该方法被调用的位置。方法正常退出时，**调用者的pc计数器的值作为返回地址，即调用该方法的指令的下一条指令的地址**。而通过异常退出的，返回地址是要通过异常表
来确定，栈帧中一般不会保存这部分信息。

​	当一个方法开始执行后，只有两种方式可以退出这个方法:

​		1.执行引擎遇到任意一个方法返回的字节码指令(return) ，会有返回值传递给上层的方法调用者，简称**正常完成出口;**
​	一个方法在正常调用完成之后究竟需要使用哪一个返回指令还需要根据方法返回值的实际数据类型而定。
​	在字节码指令中，返回指令包含ireturn (当返回值是boolean、byte、char. short和int类型时使用)、lreturn(long)、 freturn(flost)、 dreturn(double)以及areturn(引用),另外还有一个return指令供声明为void的方法、实例初始化方法、类和接口的初始化方法使用。

​		2.在方法执行的过程中遇到了异常(Exception) ，并且这个异常没有在方法内进行处理，也就是只要在本方法的异常表中没有搜索到匹配的异常处理器，就会导致方法退出。简称**异常完成出口**。

​		方法执行过程中抛出异常时的异常处理，存储在一个异常处理表，方便在发生异常的时候找到处理异常的代码。

​	本质上，方法的退出就是当前栈帧出栈的过程。此时，需要恢复上层方法的局部变量表、操作数栈、将返回值压入调用者栈帧的操作数栈、设置PC寄存器值等，让调用者方法继续执行下去。

​	**正常完成出口和异常完成出口的区别在于:通过异常完成出口退出的不会给他的.上层调用者产生任何的返回值**。

###### 一些附加信息

​		栈帧中还允许携带与Java虚拟机实现相关的一些附加信息。例如,对程序调试提供支持的信息。

# 本地方法接口

##### 什么是本地方法？

​	简单地讲，**一个Native Method就是- 一个Java调用非Java代码的接口**。一个Native Method是这样 -一个Java方法:该方法的实现由非Java语言实现，比如C。这个特征并非Java所特有，很多其它的编程语言都有这一机制，比如在C++中,你可以用extern"C"告知C++编译器去调用-一个C的函数。

​	"A native method is a Java method whose implementation isprovided by non-java code .

​	在定义一个native method时， 并不提供实现体(有些像定义一个Java interface)，因为其实现体是由非java语言在外面实现的。

​	本地接口的作用是融合不同的编程语言为Java所用，它的初衷是融合C/C++程序。

##### 为什么要使用Native Methond ?

​	Java使用起来非常方便，然而有些层次的任务用Java实现起来不容易，或者我们对程序的效率很在意时，问题就来了。

###### 与Java环境交互:

​	**有时Java应用需要与Java外面的环境交互，这是本地方法存在的主要原因**。.你可以想想Java需要与一些底层系统，如操作系统或某些硬件交换信息时的情况。本地方法正是这样-种交流机制:它为我们提供了一个非常简洁的接口，而且我们无需去了解Java应用之外的繁琐的细节。

###### 与操作系统交互:

​	JVM支持着Java语言本身和运行时库，它是Java程序赖以生存的平台，它由一个解释器(解释字节码)和一些连接到本地代码的库组成。然而不管怎样，它毕竟不是一个完整的系统，它经常依赖于一些底层系统的支持。这些底层系统常常是强大的操作系统。**通过使用本地方法，我们得以用Java实现了jre的与底层系统的交互，甚至JVM的一些部分就是用c写的**。还有，如果我们要使用一些Java语言本身没有提供封装的操作系统的特性时，我们也需要使用本地方法。

###### Sun' S Java

​	**Sun的解释器是用C实现的，这使得它能像一些普通的C一样与外部交互**。jre大部分是用Java实现的，它也通过一些本地方法与外界交互。 例如:类java. lang . Thread的setPriority ()方法是用Java实现的，但是它实现调用的是该类里的本地方法:setPriority0()。这个本地方法是用c实现的，并被植入JVM内部，在windows 95的平台上，这个本地方法最终将调用win32 setPriority() API。 这是一个本地方法的具体实现由JVM直接提供，更多的情况是本地方法由外部的动态链接库(external dynamic link library) 提供，然后被JVM调用。

​					**标识符native可以与所有其它的java标识符连用，但是abstract除外。**

###### 现状

​	**目前该方法使用的越来越少了，除非是与硬件有关的应用**，比如通过Java程序驱动打印机或者Java系统管理生产设备，在企业级应用中已经比较少见。因为现在的异构领域间的通信很发达，比如可以使用Socket通信，也可以使用web Service等等， 不多做介绍。

# 本地方法栈(Native Method Stack)

​	**Java虚拟机栈用于管理Java方法的调用而本地方法栈用于管理本地方法的调用**。

​	本地方法栈，也是线程私有的。

​	允许被实现成固定或者是可动态扩展的内存大小。(在内存溢出方面是相同的)
​		如果线程请求分配的栈容量超过本地方法栈允许的最大容量，Java虚拟机将会抛出一个StackOverflowError 异常。
​		如果本地方法栈可以动态扩展，并且在尝试扩展的时候无法申请到足够的内存，或者在创建新的线程时没有足够的内存去创建对应的本地方法栈，那么Java虛拟机将会抛出一个OutOfMemoryError 异常。

​	本地方法是使用C语言实现的。

​	它的具体做法是Native Method Stack中 登记native方法，在Execution Engine 执行时加载本地方法库。.

​	**当某个线程调用一个本地方法时，它就进入了一个全新的并且不再受虚拟机限制的世界。它和虚拟机拥有同样的权限**。
​		本地方法可以通过本地方法接口来**访问虛拟机内部的运行时数据区**。
​		它甚至可以直接使用本地处理器中的寄存器
​		直接从本地内存的堆中分配任意数量的内存。

​	**并不是所有的JVM都支持本地方法。因为Java虛拟机规范并没有明确要求本地方法栈的使用语言、具体实现方式、数据结构**等。如果JVM产品不打算支持native方法，也可以无需实现本地方法栈。

​	在Hotspot JVM中， 直接将本地方法栈和虚拟机栈合二为一。