## 文件
- Unix系统中，每个文件都位于某个目录中，逻辑上没有驱动器或卷。
- 目录是一种特殊的文件，包含很多记录，每个记录表示一个文件或子目录，目录文件永不为空。
- Unix系统将一些信息存于文件中，可以通过IO函数访问文件读取系统信息。
- 文件描述符fd是程序与文件之间的介质，程序通过fd访问和操作文件。
- 每个进程包含一个打开的文件描述符表，每个表项包含文件描述符标志与文件表项指针，每个文件表项包含文件状态标志、当前文件偏移量、v节点指针。

## IO效率
- 在用户程序中使用缓冲机制可减少系统调用次数，从而减少CPU状态切换带来的耗时，进而提高文件IO的访问效率。

## 内核缓冲技术
- 由于磁盘IO耗时大，在内核中也使用缓冲机制来提高对磁盘IO效率。内核会将磁盘上的数据块复制到内核缓冲区中，当进程向内核请求磁盘数据时，内核从缓冲区中响应请求；当进程请求的数据块不在内核缓冲区时，内核会将相应的数据块加入到请求数据列表中，然后将进程挂起，为其他进程服务；等到磁盘数据块被读入内核缓冲区后，再将数据复制到进程缓冲区中，并唤醒被挂起的进程。
- 内核缓冲技术的应用结果：1.提高了IO效率；2.优化磁盘的写操作；3.需及时将缓冲数据写入磁盘。

## 目录
- 文件包含数据，目录是文件的列表，不同目录相互连接构成树状结构，从根到当前位置经过的目录序列被称为路径。
- 目录树的深度几乎没有限制，Unix系统未对目录树的深度做限制，但是有可能建立的目录树太深超过命令允许的处理范围。
