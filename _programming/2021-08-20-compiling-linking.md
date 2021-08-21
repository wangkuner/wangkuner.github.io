---
layout: index
title: Notes of Programming
description: linking, dll
---

# Notes of Programming

不同编译器编译的目标文件可以链接的条件：需要目标文件格式相同，拥有同样的符号修饰标准，变量的内存分布方式相同，函数的调用方式相同等。

进程拥有独立的虚拟地址空间。所以可执行文件中各符号的地址空间是进程虚拟地址空间，每启动一次可执行程序，都会有一个进程创建，各进程的虚拟地址空间是独立的，所以不同的程序中符号对应的地址相同也没事。

地址重定位：编译时给程序中符号一个虚假的地址，在链接时根据地址偏移将符号地址重定位，即赋予真是的虚拟内存地址。

动态链接库装载时重定位：程序在链接时不会重定位符号地址，在装载时会有动态链接器来进行动态库的地址重定位。

**PIC**: Position Independent Code, 地址无关代码。

**ELF** (Executable linkable format, Linux系统中可执行文件格式)中共享库默认导出所有全局函数和变量。
**DLL** (Dynamic link library, windows系统中动态链接库)需要显示告诉编译器需要导出哪些符号，默认均不导出。
`__declspec(dllexport)`表示该符号从本DLL导出
`__declspec(dllimport)`表示该符号从其他DLL中导入
也可以在.def文件中声明哪些符号是导出符号
`LoadLibrary("str")`
`GetProcAddress`
`FreeLibrary`

**调用惯例(Calling convention)**规定:
- 函数参数的传递顺序和方式
- 函数栈的维护方式(压入栈的参数由函数本身或者调用方弹出)
- 名字修饰符的策略

`C`语言调用惯例：

<style>
.tablelines table, .tablelines td, .tablelines th {border: 1px solid black;}
.tablecells table, .tablelines td {padding-left: 1em; padding-right: 1em;}
</style>

| Calling conventino | 参数入栈方式 | 参数出栈执行者 | 名字修饰 |
|:------------------:|:------------:|:--------------:|:---------|
| `cdecl`            | 从右到左     | 函数调用方     | _name |
| `stdcall`          | 从右到左     | 函数本身       | _name@byteofparameters |
| `fastcall`         | 从右到左     | 函数本身       | @name@byteofparameters |
| `pascal`           | 从左到右     | 函数本身       |  |
{: .tablelines .tablecells}

`cdecl`为C语言默认调用方式，Windows API调用方式为`stdcall`。
`C++`有独特的名字修饰策略

程序的入口函数可以在链接时指定，`gcc`中由参数`-e`指定。

调用惯例与编译器有关。编译器生成ELE还是PE与平台有关。