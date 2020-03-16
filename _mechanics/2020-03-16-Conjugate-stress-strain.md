---
layout: index
title: Conjugate stresses associated with strain
---
# Conjugate stresses associated with strain[1]

In the case of large deformation, many kinds of stress, e.g. the Cauchy stress, the first and second Piola-Kirchhoff stress, and strain e.g. the Green-Lagrange strain, are defined. Some of these stresses and strain are defined in the reference configuration and others are defined in the current configuration(deformed configuration). It is critical to define the stress associated with the strain to derive the energy of the interior elastic forces.

## Tensor algebra

$\mathbf{A}$, $\mathbf{B}$ are second order tensors.
Tensor dot product is defined as 
\begin{equation}
    (\mathbf{A}\mathbf{B})_{ij}=a_{ik}b_{kj},
\end{equation}
which is equivalent to matrix prodoct.

Tensor double product is defined as
\begin{equation}
    \mathbf{A}:\mathbf{B}=\mathrm{tr}(\mathbf{A}^{T}\mathbf{B}).
\end{equation}
The tensor double product has the following properties,
\begin{equation}\label{double-product}
    \left\{\begin{array}{l}
        \mathbf{A}:\mathbf{B}=\mathrm{tr}(\mathbf{A}^{T}\mathbf{B}) = \mathrm{tr}(\mathbf{B}\mathbf{A}^{T}) = \mathrm{tr}(\mathbf{B}^{T}\mathbf{A}) = \mathrm{tr}(\mathbf{A}\mathbf{B}^{T}) = \sum\limits_{i,j=1}^{3}a_{ij}b_{ij}.\\
        \mathbf{A}:(\mathbf{B}\mathbf{C}) = (\mathbf{A}\mathbf{C}^{T}):\mathbf{B} = (\mathbf{B}^{T}\mathbf{A}):\mathbf{C}
    \end{array}\right.
\end{equation}

## Conjugate stresses associated with strain: energy aspect

The position of a material point on a body in reference configuration is denoted as $\mathbf{X}$ and 
in the current configuration (deformed) is $\mathbf{x}$. The motion of the point can be written as 
\begin{equation}
    \mathbf{x}=\mathbf{X}+\mathbf{u}
\end{equation}
where $\mathbf{u}$ is the displacement vector. The position gradient is defined as 
\begin{equation}
    \mathbf{J} = \frac{\mathrm{d}\mathbf{x}}{\mathrm{d}\mathbf{X}},
\end{equation}
which means 
\begin{equation}
    \mathrm{d}\mathbf{x}= \mathbf{J}\mathrm{d}\mathbf{X}.
\end{equation}

The equations of equilibrium established in the current configuration is 
\begin{equation}
    \left(\nabla\boldsymbol{\sigma}^{T}\right)^{T} + \mathbf{f}_{b} - \rho\ddot{\mathbf{u}} = \mathbf{0},
\end{equation}
where $\nabla=\frac{\partial}{\partial \mathbf{x}}=\left[\begin{array}{lll}
    \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z}\end{array}\right]$ 
is defined in the current configuration. $\boldsymbol{\sigma}$ is the Cauchy stress (the physical or true stress defined on the deformed configuration) tensor. 
$\mathbf{f}_{b}$ is body forces and $\rho\ddot{\mathbf{u}}$ is inertia forces.

According to virtual work principle, the weak form of the equilibrium equations are written as 
\begin{equation}\label{weak}
    \int_{v}\left[\left(\nabla\boldsymbol{\sigma}^{T}\right)^{T} + \mathbf{f}_{b} - \rho\ddot{\mathbf{u}}\right]^{T}\delta \mathbf{u}\mathrm{d}v = 0.
\end{equation}

One can show that 
\begin{equation}
    \nabla(\boldsymbol{\sigma}\delta \mathbf{u})=(\nabla\boldsymbol{\sigma})\delta\mathbf{u} + \boldsymbol{\sigma}:\frac{\partial(\delta\mathbf{u})}{\partial\mathbf{x}},
\end{equation}
where
\begin{equation}
    \frac{\partial(\delta\mathbf{u})}{\partial x} = \frac{\partial(\delta\mathbf{u})}{\partial\mathbf{X}}\frac{\partial\mathbf{X}}{\partial\mathbf{x}} = \delta\frac{\partial\mathbf{x}}{\partial\mathbf{X}}\mathbf{J}^{-1} = (\delta\mathbf{J})\mathbf{J}^{-1},
\end{equation}
because of $\delta\mathbf{u}=\delta\mathbf{x}$.

Substituting the preceeding two equations into Eq.(\ref{weak}) and using Gauss theorem, we can obtain
\begin{equation}
    \int_{s}\mathbf{n}^{T}\boldsymbol{\sigma}\delta\mathbf{u}ds - \int_{v}\boldsymbol{\sigma}:(\delta\mathbf{J})\mathbf{J}^{-1}dv + \int_{v}\left(\mathbf{f}_{b}-\rho\ddot{\mathbf{u}}\right)^{T}\delta\mathbf{u}dv=0,
\end{equation}
where $s$ is the surface area and $\mathbf{n}$ is unit normal to the surface. 
The second integral is the virtual work of the internal elastic forces and is defined as 
\begin{equation}\label{interior-energy}
    \delta W_{int} = -\int_{v}\boldsymbol{\sigma}:(\delta\mathbf{J})\mathbf{J}^{-1}dv.
\end{equation}
The volumes of amaterial element in the reference configuration $dV$ and current configuration $dv$ are related by
\begin{equation}
    dv=JdV,
\end{equation}
where $J=\mathrm{det}(\mathbf{J})$. The Eq.(\ref{interior-energy}) can be written as 
\begin{equation}\label{interior-energy-reference}
    \delta W_{int} = -\int_{V}J\boldsymbol{\sigma}:(\delta\mathbf{J})\mathbf{J}^{-1}dV.
\end{equation}
The tensor $\boldsymbol{\sigma}_{K}=J\boldsymbol{\sigma}$ is called the Kirchhoff stress tensor.

Subsequent derivations need Nanson's formula which is represented as 
\begin{equation}\label{nanson}
    \mathbf{N}=\frac{1}{J}\mathbf{J}^{T}\mathbf{n}\frac{\mathrm{d}s}{\mathrm{d}S},
\end{equation}
where $\mathbf{N}$ is a unit normal to the surface in the reference configuration and $\mathbf{n}$ is the corresponding vector in the current configuration. 
$dS$ is the element area in the reference configuration and $ds$ is the corresponding area in the current configuration.

Based on the Cauthy stress formula $\boldsymbol{\sigma}_{n}=\boldsymbol{\sigma}\mathbf{n}$ 
where $\boldsymbol{\sigma}_{n}$ is the surface traction, 
the force acting on a surface with a unit normal $\mathbf{n}$ is 
\begin{equation}\label{force}
    \mathbf{f}=\boldsymbol{\sigma}\mathbf{n}ds.
\end{equation}
Substituting the Nanson's formula into Eq.(\ref{force}), 
we can obtain the force written in terms of the normal and area defined in the reference configuration as 
\begin{equation}\label{force-reference}
    \mathbf{f}=J\boldsymbol{\sigma}(\mathbf{J}^{T})^{-1}\mathbf{N}dS.
\end{equation}
From Eq.(\ref{force-reference}), we can define another stress measure, the so called first Piola-Kirchhoff(PK) stress,  
\begin{equation}
    \boldsymbol{\sigma}_{PK1}=J\boldsymbol{\sigma}(\mathbf{J}^{T})^{-1}.
\end{equation}
The first Piola-Kirchhoff stress can be used to define tractions in terms of the normal and area 
in the reference configuration but it is not a symmetric tensor.
Combining Eq.(\ref{double-product}), we can write the virtual work of the internal elastic forces in terms of 
the first PK stress as 
\begin{equation}\label{interior-energy-PK1}
    \delta W_{int} = -\int_{V}\boldsymbol{\sigma}_{PK1}:\delta\mathbf{J}dV.
\end{equation}
Eq.(\ref{interior-energy-PK1}) shows that the first PK stress $\boldsymbol{\sigma}_{PK1}$ is associated
with the matrix of the position vector gradients $\mathbf{J}$.

The Green–Lagrange strain tensor is defined as 
\begin{equation}
    \boldsymbol{\epsilon} = \frac{1}{2}\left(\mathbf{J}^{T}\mathbf{J}-\mathbf{I}\right)
\end{equation}
The variation of the  Green–Lagrange strain is 
\begin{equation}
    \delta\boldsymbol{\epsilon} = \frac{1}{2}\left(\mathbf{J}^{T}\delta\mathbf{J} + \delta\left(\mathbf{J}^{T}\right)\mathbf{J}\right).
\end{equation}
Using the identities of Eq.(\ref{double-product}) we can write the virtual work of the internal elastic forces in terms of 
the Green–Lagrange strain as 
\begin{equation}\label{interior-energy-C-G-strain}
    \delta W_{int} = -\int_{V}J\boldsymbol{\sigma}:(\mathbf{J}^{-1})^{T}\delta\boldsymbol{\epsilon}\mathbf{J}^{-1}dV.
\end{equation}
Using the properties of the tensor double product(Eq.(\ref{double-product})), we can rewrite Eq.(\ref{interior-energy-C-G-strain}) as 
\begin{equation}\label{interior-energy-PK2}
    \delta W_{int} = -\int_{V}\left(J\mathbf{J}^{-1}\boldsymbol{\sigma}(\mathbf{J}^{-1})^{T}\right):\delta\boldsymbol{\epsilon}dV = \int_{V}\boldsymbol{\sigma}_{PK2}:\delta\boldsymbol{\epsilon}dV.
\end{equation}
where $\boldsymbol{\sigma}_{PK2}$ is the second Piola–Kirchhoff stress tensor defined as 
\begin{equation}\label{PK2}
    \boldsymbol{\sigma}_{PK2} = J\mathbf{J}^{-1}\boldsymbol{\sigma}(\mathbf{J}^{-1})^{T}
\end{equation}


The Cauchy stress tensor is not associated with the Green–Lagrange strain tensor 
because the Cauchy stress tensor is defined in the current (deformed) configuration, 
whereas the Green–Lagrange strain tensor is defined in the reference configuration. 
According to Eq.(\ref{interior-energy-reference}), the Cauchy stress is associated with $\dot{\mathbf{J}}\mathbf{J}$. 
Eq.(\ref{interior-energy-PK1}) shows that the first Piola-Kirchhoff stress is associated with the deformation gradient. 
However, the deformation gradient matrix $\mathbf{J}$ does not remain constant under an arbitrary rigid-body motion.
So, it is not an appropriate measure of the deformation.
Eq.(\ref{interior-energy-PK2}) shows that the second Piola–Kirchhoff stress tensor is associated with the Green–Lagrange strain tensor.


[1] Shabana A.A. Computational Continuum Mechanics, 3rd Edition. John Wiley \& Sons, Ltd. 2018.