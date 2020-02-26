---
layout: index
title: Cblas on Windows
description: scientific computation
---

# Cblas on Windows

 1. Download the [BLAS](http://www.netlib.org/blas/) source and [cBLAS](http://www.netlib.org/blas/) source and copy the `blas` folder into `cblas` folder. The directory tree is as following,
 ```
 +cblas
 |  +blas
 |  +include
 |  +lib
 |  +src
 |  Makefile
 ```
 2. The minGW is needed on windows. The [minGW-m64](https://mingw-w64.org) is advanced.
 3. The file `xerbla.f` in `blas` directory is overrided by the corresponding c file in `src` directory so it should be remove away.
 4. The BLAS are written in fortran so it should be compiled by fortran compilers such as `gfortran`. The cBLAS is the c interface for call blas from c and it should be compiled by c compilers such as `gcc`. The library should be linked by `gfortran` compilers. Run the following `makefile` script in the root directory and the library file `cblas_x86_64.dll`, `cblas_x86_64.lib`, `cblas_x86_64.def` would be obtained. 

```makefile
DIR_SRC=./src
DIR_CBLAS_SRC=./cblas

C_SRC = $(wildcard $(DIR_SRC)/*.c)
C_OBJ=$(patsubst %.c,%.o,$(SRC))

F_BLAS_SRC = $(wildcard $(DIR_BLAS_SRC)/*.f)
F_BLAS_OBJ=$(patsubst %.f,%.o,$(F_BLAS_SRC))

F_C_SRC = $(wildcard $(DIR_SRC)/*.f)
F_C_OBJ=$(patsubst %.f,%.o,$(F_C_SRC))

CBLAS=cblas_x86_64.dll

CC=gcc
FC=gfortran
CFLAGS=-I./include -O3 -m64 -DADD_
FCFLAGS=-O3 -m64

ALL:CBLAS

CBLAS:$(C_OBJ) $(F_BLAS_OBJ) $(F_C_OBJ)
	$(FC) -shared -o $@ $(C_OBJ) $(F_BLAS_OBJ) $(F_C_OBJ) -Wl,--output-def,cblas_x86_64.def,--out-implib,cblas_x86_64.lib

$(C_OBJ):%.o:$(DIR_SRC)/%.c
	$(CC) $(CFLAGS) -c $< -o $@

$(F_BLAS_OBJ):%.o:$(DIR_BLAS_SRC)/%.f
	$(FC) $(FCFLAGS) -c $< -o $@
$(F_C_OBJ):%.o:$(DIR_SRC)/%.f
	$(FC) $(FCFLAGS) -c $< -o $@
	
.PHONY:clean

clean:
	del /f $(C_OBJ) $(F_BLAS_OBJ) $(F_C_OBJ)
```
