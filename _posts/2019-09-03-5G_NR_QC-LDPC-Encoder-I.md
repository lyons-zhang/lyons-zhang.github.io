---
title: 5G NR QC-LDPC Encoder I
description: 
categories: 
---

>  5G has been focused on structured LDPC codes known as quasi-cyclic low-density parity-check (QC-LDPC) codes, which exhibit advantages over other types of LDPC codes with respect to the hardware implementations of encoding and decoding using simple shift registers and logic circuits.  
### **5G NR QC-LDPC**  
##### **Circulant Permutation Matrix**
A circular permutation matrix $${\bf I}(P_{i,j})$$ of size $$Z_c \times Z_c$$ is obtained by circularly shifting the identity matrix $$\bf I$$ of size $$Z_c \times Z_c$$ to the right $$P_{i,j}$$ times. We denoted this binary circulant permutation matrixas by $$Q(P_{i,j})$$, considering $$Q(1)$$ as an example,  
<center>$$\begin{bmatrix}
0 & 1 & 0 & \ldots & 0\cr
0 & 0 & 1 & \ldots & 0\cr
0 & 0 & 0 & \ldots & 1\cr
\vdots & \vdots & \ddots & \vdots \cr
1 & 0 & 0 & \ldots & 0\cr
\end{bmatrix}$$</center>
For simple notation, $$Q(−1)$$ denotes the null matrix.  
All possible lifting sizes $$Z_c$$ are listed as follow^{[1]}:  
![ldpcLift]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201909/ldpcLift.png){:.aligncenter}  


  
Reference:  
1. 3GPP TS 38.212. "NR; Multiplexing and channel coding." 3rd Generation Partnership Project. Technical Specification Group Radio Access Network.