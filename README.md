# Unix-Linux Programming

## 关于系统编程
- 系统资源：计算机系统包含很多系统资源，例如处理器、IO、进程、内存、设备、计时器、通信与网络等。每种内核服务都有自身的特点，使用的设备不同，参数不同，提供的数据也不同，需要掌握内核服务的机制，以便在用户程序中使用服务。<br>
- 用户程序：用户程序一般利用系统资源对数据进行存储、转换和处理。用户程序访问设备必须经过内核，内核通过开放系统调用API使得程序可访问系统资源。<br>
- 系统调用：系统调用的开销是由于内存拷贝、特殊的堆栈设置以及内存环境准备而造成的。<br>

## 学习方法
分析现有的例程-->学习系统调用API-->编程实现，编程练习中需要考虑程序的目的、实现方法、动手实践、总结经验。

## 调试环境
Linux 5.4.0-110-generic #124~18.04.1-Ubuntu SMP x86_64 GNU/Linux

## 用户角度的Unix
- 用户登录管理
- 目录操作
- 文件操作

## 系统角度的Unix
- 信息交换
- 资源的管理及分配
- 网络访问
- 面向用户

## Tips
- 使用Linux系统中自带的manual手册查询shell命令与系统调用的具体信息与用法，使用man命令查询。
