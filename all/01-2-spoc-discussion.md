# lec1: 操作系统概述

---

## **提前准备**

（请在上课前完成）

* 完成lec1的视频学习和提交对应的在线练习
* git pull ucore\_os\_lab, ucore\_os\_docs, os\_tutorial\_lab, os\_course\_exercises in github repos。这样可以在本机上完成课堂练习。
* 知道OS课程的入口网址，会使用在线视频平台，在线练习/实验平台，在线提问平台\(piazza\)
  * [http://os.cs.tsinghua.edu.cn/oscourse/OS2019spring](http://os.cs.tsinghua.edu.cn/oscourse/OS2019spring)


* 会使用linux shell命令，如ls, rm, mkdir, cat, less, more, gcc等，也会使用linux系统的基本操作。
* 在piazza上就学习中不理解问题进行提问。



# 思考题

## 填空题

* 当前常见的操作系统主要用__C语言和汇编__编程语言编写。
* "Operating system"这个单词起源于__Operator__ 。
* 在计算机系统中，控制和管理__各种资源__ 、有效地组织__多道程序__运行的系统软件称作__操作系统__ 。
* 允许多用户将若干个作业提交给计算机系统集中处理的操作系统称为__批处理__操作系统
* 你了解的当前世界上使用最多的操作系统是__Android__ 。
* 应用程序通过__系统调用__接口获得操作系统的服务。
* 现代操作系统的特征包括__并发性__ ，__虚拟性__ ，__异步性__ ，__共享性和持久性__ 。
* 操作系统内核的架构包括__宏内核__ ，__微内核__ ，__外核__ 。


## 问答题

- 请总结你认为操作系统应该具有的特征有什么？并对其特征进行简要阐述。

  从总体上看，操作系统具有五个方面的特征：
  虚拟性：虚拟性是一种管理技术，把物理上的一个实体变成逻辑上的多个对应物，或把物理上的多个实体变成逻辑上的一个对应物的技术。采用虚拟技术的目的是为用户提供易于使用、方便高效的操作环境。
  并发性：是指两个或多个事件在同一时间间隔内发生。操作系统的并发性是指计算机系统中同时存在多个运行着的程序，因此它应该具有处理和调度多个程序同时执行的能力。
  异步性：在多道程序环境下，允许多个程序并发执行，但由于资源有限，进程的执行不是一贯到底。而是走走停停，以不可预知的速度向前推进，这就是进程的异步性。异步性使得操作系统运行在一种随机的环境下，可能导致进程产生与时间有关的错误。但是只要运行环境相同，操作系统必须保证多次运行程序，都获得相同的结果。
  共享性：是指系统中的资源（硬件资源和信息资源）可以被多个并发执行的程序共同使用，而不是被其中一个独占。资源共享有两种方式：互斥访问和同时访问。
  持久性：操作系统提供了文件系统来做一个持久性的存储。

- 为什么现在的操作系统基本上用C语言来实现？为什么没有人用python，java来实现操作系统？

  C语言足够高级，成熟，可以方便编写OS和跨平台；
  C语言足够底层，能够很好地描述计算机硬件细节（比如位操作）；
  C编译器可以生成高效的机器语言组成的执行代码，性能有保证；
  C语言产生的一个原因就是为了更好地编写UNIX操作系统。
  而python和java无法保证性能，不够底层。
  
---

## 可选练习题

---

- 请分析并理解[v9\-computer](https://github.com/chyyuu/os_tutorial_lab/blob/master/v9_computer/docs/v9_computer.md)以及模拟v9\-computer的em.c。理解：在v9\-computer中如何实现时钟中断的；v9 computer的CPU指令，关键变量描述有误或不全的情况；在v9\-computer中的跳转相关操作是如何实现的；在v9\-computer中如何设计相应指令，可有效实现函数调用与返回；OS程序被加载到内存的哪个位置,其堆栈是如何设置的；在v9\-computer中如何完成一次内存地址的读写的；在v9\-computer中如何实现分页机制。


- 请编写一个小程序，在v9-cpu下，能够输出字符


- 输入的字符并输出你输入的字符


- 请编写一个小程序，在v9-cpu下，能够产生各种异常/中断


- 请编写一个小程序，在v9-cpu下，能够统计并显示内存大小



- 请分析并理解[RISC-V CPU](http://www.riscvbook.com/chinese/)以及会使用模拟RISC\-V(简称RV)的qemu工具。理解：RV的特权指令，CSR寄存器和在RV中如何实现时钟中断和IO操作；OS程序如何被加载运行的；在RV中如何实现分页机制。
  - 请编写一个小程序，在RV下，能够输出字符
  - 输入的字符并输出你输入的字符
  - 请编写一个小程序，在RV下，能够产生各种异常/中断
  - 请编写一个小程序，在RV下，能够统计并显示内存大小

## 参考资料
 - [Intel格式和AT&T格式汇编区别](http://www.cnblogs.com/hdk1993/p/4820353.html)
 - [x86汇编指令集  ](http://hiyyp1234.blog.163.com/blog/static/67786373200981811422948/)
 - [PC Assembly Language, Paul A. Carter, November 2003.](https://pdos.csail.mit.edu/6.828/2016/readings/pcasm-book.pdf)
 - [*Intel 80386 Programmer's Reference Manual*, 1987](https://pdos.csail.mit.edu/6.828/2016/readings/i386/toc.htm)
 - [IA-32 Intel Architecture Software Developer's Manuals](http://www.intel.com/content/www/us/en/processors/architectures-software-developer-manuals.html)
 - [v9 cpu architecture](https://github.com/chyyuu/os_tutorial_lab/blob/master/v9_computer/docs/v9_computer.md)
 - [RISC-V cpu architecture](http://www.riscvbook.com/chinese/)
 - [OS相关经典论文](https://github.com/chyyuu/aos_course_info/blob/master/readinglist.md)
