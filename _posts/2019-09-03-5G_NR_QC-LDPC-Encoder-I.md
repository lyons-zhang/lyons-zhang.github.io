---
title: 5G NR QC-LDPC Encoder I
description: 
categories: 
---

>  5G has been focused on structured LDPC codes known as quasi-cyclic low-density parity-check (QC-LDPC) codes, which exhibit advantages over other types of LDPC codes with respect to the hardware implementations of encoding and decoding using simple shift registers and logic circuits.  

### **5G NR QC-LDPC**  
##### **Circulant Permutation Matrix**  
A circular permutation matrix $${\bf I}(P_{i,j})$$ of size $$Z_c \times Z_c$$ is obtained by circularly shifting the identity matrix $$\bf I$$ of size $$Z_c \times Z_c$$ to the right $$P_{i,j}$$ times. We denoted this binary circulant permutation matrixas by $$Q(P_{i,j})$$, considering $$Q(1)$$ as an example,  
<center>$$Q(1) = \begin{bmatrix}
0 & 1 & 0 & \ldots & 0\cr
0 & 0 & 1 & \ldots & 0\cr
\vdots & \vdots & \ddots & \vdots \cr
0 & 0 & 0 & \ldots & 1\cr
1 & 0 & 0 & \ldots & 0\cr
\end{bmatrix}$$</center>
For simple notation, $$Q(−1)$$ denotes the null matrix.  
All possible lifting sizes $$Z_c$$ are listed as $$\text{follow}^{[1]}$$:  
![ldpcLift]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201909/ldpcLift.png){:.aligncenter}  
The parity-check matrix H of QC-LDPC code expressed by the following $$mb \times nb$$ array of $$Z \times Z$$ circulants over GF(2):  
<center>$$H = \begin{bmatrix}
Q(P_{1,1}) & Q(P_{1,2}) & \ldots & Q(P_{1,n_b})\cr
Q(P_{2,1}) & Q(P_{2,2}) & \ldots & Q(P_{2,n_b})\cr
\vdots & \vdots & \ddots & \vdots \cr
Q(P_{m_b,1}) & Q(P_{m_b,2}) & \ldots & Q(P_{m_b,n_b})\cr
\end{bmatrix}$$</center>
##### **Circulant Permutation Matrix**
There are two rate-compatible base graphs with similar structures in 5G NR, denoted by BG1 and BG2. BG1 is targeted for larger block lengths$$(500 \le K \le 8448)$$ and higher rates $$(1/3 ≤ R ≤ 8/9)$$, whereas BG2 is targeted for smaller block lengths$$(40 \le K \le 2560)$$ and lower rates $$(1/5 \le R \le 2/3)$$.  
For BG1, a matrix of $$\bf{H}_{BG}$$ with a size of $$m_b \times n_b(m_b = 46, n_b = 68)$$.
For BG2, a matrix of $$\bf{H}_{BG}$$ with a size of $$m_b \times n_b(m_b = 42, n_b = 52)$$.
  
Reference:  
1. 3GPP TS 38.212. "NR; Multiplexing and channel coding." 3rd Generation Partnership Project. Technical Specification Group Radio Access Network.