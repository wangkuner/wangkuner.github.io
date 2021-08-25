---
layout: index
title: Installation of Siconos
description: linking, dll
---

# Installation of Siconos

Siconos is an open-source scientific software primarily targeted at modeling and simulating nonsmooth dynamical systems in C++ and in Pytho.

According to the requirements, only the essential components, *externals*, *numerics* and *kernel*, are installed. 
It can be seen from the following picture that the components *numerics and *kernel* depend on *externals*. 

![Siconos components](https://nonsmooth.gricad-pages.univ-grenoble-alpes.fr/siconos/_images/siconos_components.png)

To use the *mkl blas* and *lapack*, the following variables should be added to the CMakeLists.txt file.

```cmake
set(BLA_VENDER Intel10_64lp)
set(BLAS_INCLUDE_DIR "/opt/intel/oneapi/mkl/2021.3.0/include")
set(BLAS_LIBRARIES "/opt/intel/oneapi/mkl/2021.3.0/lib/intel64/libmkl_core.so")
set(LAPACK_LIBRARIES "/opt/intel/oneapi/mkl/2021.3.0/lib/intel64/libmkl_core.so")
set(LAPACK_INCLUDE_DIR "/opt/intel/oneapi/mkl/2021.3.0/include")
set(CBLAS_LIBRARY "/opt/intel/oneapi/mkl/2021.3.0/lib/intel64/libmkl_core.so")
set(BLAS_iomp5_LIBRARY /opt/intel/oneapi/compiler/latest/linux/compiler/lib/intel64_lin/libiomp5.so)
```

Otherwise, the FindBLASDEV would not find the blas library.

The *Siconos* also depends on the boost and *gmp*. The two libraries should be installed. 

The `WITH_FORTRAN` option should be ON.

The if the cmake can not generate some MACROs automatically, these MACROs can be defined manually. 

The installation on Windows is very complex. You should successfully install the *gmp* library first.