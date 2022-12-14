
# Chapter 1
## 1.1
bit是0/1，1byte=8bit。
只由ASCII构成的文件叫做文本文件， 其他的叫做二进制文件。
## 1.2 程序被其他程序翻译成不同的格式
由源文件到目标文件的转化是由**编译器**完成的。
例如
```
linux> gcc -o hello hello.c
```
预处理器（cpp），编译器（ccl），汇编器（as），链接器（ld）共同构成编译系统（compilation system）。

* 预处理阶段。将#开头的命令插入到程序文本中。以.i结尾
* 编译阶段。
* 汇编器（as）
* 链接器（ld）
##  1.3 了解编译系统的用处
* 优化程序性能
* 理解bug
* 避免bug
## 1.4 处理器读并解释储存在内存中的指令
### 1.4.1系统硬件组成
* **1** 总线
* **2** I/O设备
键盘，鼠标，显示器，磁盘。通过控制器或者适配器与I/O主线相连，传递信息。
* **3** 主存
* **2** 处理器
#### 1.4.2
## 1.5 高速缓存
性价比高，cache还能存储访问量高的数据。
## 1.6 存储设备形成层次结构
register，L1，L2，L3，主存，磁盘
## 1.7 操作系统管理硬件
应用程序对硬件的操作尝试都必须通过操作系统，是两者的媒介，两者不能直接相互操作。
### 1.7.1 进程
程序并不是独占整个计算机。进程是操作系统对一个正在运行的程序的一种抽象。一个系统可以同时运行多个进程，而每个进程都好像在独占使用硬件。一个进程的指令和另一个进程的指令交错进行，叫做并发运行。操作系统实现这种交错执行的机制称作上下文切换。
### 1.7.2 线程
一个进程可以由多个线程执行，共享同样的代码和数据。
### 1.7.3 虚拟内存
想起了一个好玩的事情。写acm的cpp的时候，经常会遇到爆战，但这里说栈和堆都是动态伸展扩张的。查了查资料发现，有的操作系统不是无限动态增长的，会有一个限制，因为这样栈太大一般都不是什么好事情。还有stackoverflow.com的名字由来。
## 1.8 系统之间利用网络通信
## 1.9
### 1.9.1 Amdahl定律
总结：单纯的提升某个硬件，即使加速到无限快，对整个操作系统的提升也是有限制的，只有通过优化系统的大部分组件才能获得跟高的提升。
### 1.9.2 并发和并行
并发（concurrency）是同时具有多个活动的系统，并行（parallellism）是同时的进行多个并发来从真正的实现同时运行。
* 1 线程级并发
构建在进程之上，能进行多个程序的执行的系统，但就像杂耍抛球一样，并不是真正意义上的手握所有球。但依托多线程处理器（多核和多线程），提高了性能，减少了模拟并发的需求量，只有多线程处理器才能实现并行。
多核处理器， 每个核有单独的L1和L2缓存和共享的L3缓存。
超线程，一般是同时两个线程，提升近乎一半的性能。
* 2 指令集并发
* 3 单指令、多数据并发
### 1.9.3 计算机系统中抽象的重要性
无需知道内部的工作和具体内容。
文件是对I/O设备的抽象，虚拟内存是对程序储存器的抽象，进程是对正在运行的程序的抽象。
虚拟机。