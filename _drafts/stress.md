

  <!-- <script src="mathjax-config.js" defer></script> -->
<script  type="text/javascript">MathJax = {tex: { inlineMath: [['$', '$'], ['\\(', '\\)']], tags:'ams' }};</script>
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script type="text/javascript" id="mathjax-script" defer src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-svg.js"></script>

# Stress

**Engineering stress**, namely nominal stress, is defined at the reference configuration and just applies to small deformations.
**Cauchy stress**, namely true stress, is defined at the current configuration and can be usded for large deformations.

stress versus surface traction

## Why a stress tensor has nine components?

The mapping: $\boldsymbol{\sigma}: \mathbf{n}\rightarrow \boldsymbol{\sigma}_{n}$ is a linear map from vector to  vector which is a tensor of rank one. According to quotient principle,  the stress state at one point should be a rank two tensor.

一点的应力状态将微元方向映射为物质点在该微元面上的应力，即将方向向量映射为应力向量，而向量为一阶张量，根据张量运算商法则，应力状态应该用一个二阶张量表示。

## Why a stress tensor can be expressed by the stress in three infinitesimal area with different direction?

