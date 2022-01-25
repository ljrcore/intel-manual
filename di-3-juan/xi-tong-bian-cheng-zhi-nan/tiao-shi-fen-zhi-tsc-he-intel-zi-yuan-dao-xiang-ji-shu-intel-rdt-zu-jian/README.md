# 调试、分支、TSC和Intel资源导向技术（Intel® RDT）组建

英特尔64和IA-32架构提供了用于调试代码和监控性能的调试组件。这些组件对于调试应用软件、系统软件和多任务操作系统很有价值。调试是通过调试寄存器（DR0到DR7）和特定型号的寄存器（MSRs）来访问：

* 调试寄存器保存内存和I/O位置的地址，称为断点。断点是用户在程序中选择的内存数据存储区或特定I/O端口的位置。它们被设置在程序员或系统设计者希望程序在执行中停止的位置，并通过调用调试软件检查处理器的状态。当对断点地址进行内存或I/O访问时，会产生一个调试异常（#DB）。
* MSR监控分支、中断和异常。它们记录中断或异常最后一个分支的地址，以及在中断或异常发生以前之前最后一个分支的地址。
* 第17.17节"Time-Stamp Counter"介绍了时间戳计数器。
* 第17.18节 "Intel® Resource Director Technology (Intel® RDT) Monitoring Features"中介绍了允许监控共享平台资源（如L3高速缓存）的功能。
* 第17.19节 "Intel® Resource Director Technology (Intel® RDT) Allocation Features "中介绍了能够控制共享平台资源的功能。

> Intel 64 and IA-32 architectures provide debug facilities for use in debugging code and monitoring performance. These facilities are valuable for debugging application software, system software, and multitasking operating systems. Debug support is accessed using debug registers (DR0 through DR7) and model-specific registers (MSRs):
>
> * Debug registers hold the addresses of memory and I/O locations called breakpoints. Breakpoints are user- selected locations in a program, a data-storage area in memory, or specific I/O ports. They are set where a programmer or system designer wishes to halt execution of a program and examine the state of the processor by invoking debugger software. A debug exception (#DB) is generated when a memory or I/O access is made to a breakpoint address.
> * MSRs monitor branches, interrupts, and exceptions; they record addresses of the last branch, interrupt or exception taken and the last branch taken before an interrupt or exception.
> * Time stamp counter is described in Section 17.17, “Time-Stamp Counter”.
> *   Features which allow monitoring of shared platform resources such as the L3 cache are described in Section
>
>     17.18, “Intel® Resource Director Technology (Intel® RDT) Monitoring Features”.
> * Features which enable control over shared platform resources are described in Section 17.19, “Intel® Resource Director Technology (Intel® RDT) Allocation Features”.

注意：

本章多次提到了最后分支记录（LBR）。除非另有说明，本章中所有这些参考都是指该功能的早期非架构形式。第18章定义了在较新的处理器上支持的最后分支记录的架构形式。

> Note：
>
> This chapter makes numerous references to last-branch recording (LBR) facilities. Unless noted otherwise, all such references in this chapter are to an earlier non-architectural form of the feature. Chapter 18 defines an architectural form of last-branch recording that is supported on newer processors.
