---
title:   Polar Coding Notes III
description: 
categories: Digital Comunication
---

>  For any B-DMC $$W$$, the channels $${\W_N^{(i)}\}$$ polarize in the sense that, for any fixed $$\delta \in (0, 1)$$, as $$N$$ goes to infinity through powers of two, the fraction of indices $$i \in \{1, \dots, N\}$$ for which $$I(W_N^{(i)}) \in (1 − \delta, 1]$$ goes to $$I(W)$$ and the fraction for which $$I(W_N^{(i)}) \in [0, \delta)$$ goes to $$1−I(W)^{[1]}$$.
  
#### **Channel Combining**  
Channel combining is a step that combines copies of a given B-DMC $$W$$ in a recursive manner to produce a vector channel $$W_N : {\cal X}^N \to {\cal Y}^N$$, where $$N$$ can be any power of two, $$N=2^n, n\le0^{[1]}$$.  
The notation $$u_1^N$$ as shorthand for denoting a row vector $$(u_1, \dots , u_N)$$.  
The vector channel **$$W_N$$** is the virtual channel between the input sequence $$u_1^N$$ to a linear encoder and the output sequence $$y^N_1$$ of $$N$$ copies of the original channel $$W$$. $$W_1 = W$$ is one copy of $$W$$.  
We use $$W^N : {\cal X}^N \to {\cal Y}^N$$ to denote the vector channel between the input sequence $$x_1^N$$ and the output sequence $$y_1^N$$ of $$N$$ copies of the original channel $$W$$.  
![w2]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201810/w2.png){:.aligncenter}   
<center>$$W_N(y_1^N|u_1^N) = W^N(y_1^N|u_1^NG_N) = W^N(y_1^N|x_1^N) = \sum_{i=1}^N W(y_i|x_i)$$</center>  
for any $$N = 2^n, n \le 0$$,  
<center>$$G_N = B_N F^{\bigotimes n}$$</center>  
where $$B_N$$ is a permutation matrix known as **bit-reversal**, $$F \triangleq \left[\begin{smallmatrix}1 & 0\cr 1 & 1 \end{smallmatrix}\right]$$ and $$\bigotimes n$$ is **Kronecker power**.  
The *bit-reversal* is shown as below from$$^{[8]}$$  
![bitreversal]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201810/bitreversal.png){:.aligncenter}   
Sort a data sequence in nomal order by successive examination of the MSB as the left in the picture.  
Sort the sequence $$x[n]$$ as the permutation matrix(sequence A030109 in the OEIS) order, such a separation of odd and even can be carried out by examining the LSB.  
The recursive construction of $$W_N$$ from two copies of $$W_{N/2}$$ is useful for software and hardware$$^{[9]}$$. But for hardware implementation, the "rewire" structure is more attractive:  
![rewire]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201810/rewire.png){:.aligncenter}   

The coding scheme for $$U_1,U_2 \, \overset{i.i.d.}{\sim} \, Unif\{0,1\}$$.  
It is easy to see that $$U_1, U_2$$ and $$X_1, X_2$$ have a bijection, and further coupling this with the fact $$X_1,X_2 \, \overset{i.i.d.}{\sim} \, Unif\{0,1\}$$. We have  
<center>$$I(U_1,U_2;Y_1,Y_2) = I(X_1,X_2;Y_1,Y_2) = 2C = 2I(W)$$</center>  
and for $$U_1, \dots, U_N \, \overset{i.i.d.}{\sim} \, Unif\{0,1\}$$, then $$X_1, \dots, X_N \, \overset{i.i.d.}{\sim} \, Unif\{0,1\}$$   
<center>$$I(U^N;Y^N) = I(X^N;Y^N) = NI(W)$$</center>  
<center>$$\eqalign{I(X^N;Y^N) &= H(Y^N) - H(Y^N|X^N) &= H(Y^N) - \sum_{i=1}^N H(Y_i|Y_1, ... , Y_{i-1}, X^N) &= \sum_{i=1}^N H(Y_i) - \sum_{i=1}^N H(Y_i|X_i) &= \sum_{i=1}^N I(X_i;Y_i)}$$</center>




#### **Channel Splitting**  

Reference:  
1. E. Arikan. *Channel polarization: A method for constructing capacity-achieving codes for symmetric binary-input memoryless channels*. IEEE Trans. on Information Theory, vol.55, no.7, pp.3051–3073, July 2009.  


