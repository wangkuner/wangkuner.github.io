---
layout: index
title: Bits Problems in Crossplat Programming
description: scientific computation
---

# Bits Problems in Crossplat Programming

Size of some data types in different data models:
<style>
.tablelines table, .tablelines td, .tablelines th {border: 1px solid black;}
.tablecells table, .tablelines td {padding-left: 1em; padding-right: 1em;}
</style>

| data type | ILP32 | LP64 | LLP64 | ILP64 |
|:---------:|:-----:|:----:|:-----:|:-----:|
| int       |   32  |  32  |  32   |  32   |
| long      |   32  |  64  |  32   |  64   |
| long long |   64  |  64  |  64   |  64   |
| float     |   32  |  32  |  64   |  64   |
| double    |   64  |  64  |  64   |  64   |
| pointer   |   32  |  64  |  64   |  64   |
{: .tablelines .tablecells}

64-bit windows system uses LLP64 model. Most 64-bit unix and unix-like system uses LP64 model.

Problems should be avoided in using MKL pardiso:
The first parameter of MKL pardiso `pt[64]` should be 4 bytes on 32-bit system and be 8 bytes on 64-bit systems, namely, it can be defined as

```c++
int pt[64];         //on  32-bit system
long long pt[64];   //on  64-bit system
```

I typedefed my own data from `long` type for the integer type so pointers of integer type are all of `long *` type in my program. However, the data type of pointer parameters of MKL pardiso is `int *`. Unsuprisingly my program dumped. It took me two days to find the bug.

Summary: Type conversions should be careful in `c++`. Pointers pointing to different types should not be assigned to each other.