## top
VIRT:
	1. 进程需要的虚拟内存大小，包括进程使用的库、代码、数据以及malloc，new分配的堆空间  
	和分配的栈空间等；
	2. 不是进程当前使用的内存大小。
	3. VIRT = SWAP + RES
	
RES:
	1. 进程当前使用的内存大小，包括使用中的malloc、new分配的堆空间和栈空间，但不包括swap out量
	2. 包括其他进程的共享
	3. 关于库占用内存的情况，它只统计加载库文件所占内存大小
	4. RES = CODE + DATA

SHR：
	1. 除了自身进程共享内存，也包括其他进程的共享内存
	2. 虽然进程只使用了几个共享库函数，但他只包含整共享库的大小。
	3. 计算某个进程所占的物理内存大小公式： RES - SHR：
	4. swap out后，它将会降下来
