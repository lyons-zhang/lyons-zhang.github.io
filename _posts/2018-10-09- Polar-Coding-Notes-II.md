---
title:   Polar Coding Notes II
description: 
categories: Digital Comunication
---

>  Random codes achieve capacity but their encoding and decoding is inefficient because they do not have a 'nice structure'. Polar codes overcome this problem by splitting the channels into noiseless and useless channels. The noiseless channels preserve the encoding structure and therefore, for the information passed only over these noiseless channels, decoding can be done efficiently.
  
#### **Channel Combining**  
Channel combining is a step that combines copies of a given B-DMC $$W$$ in a recursive manner to produce a vector channel $$W_N : {\cal X}^N \to {\cal Y}^N$$, where $$N$$ can be any power of two, $$N=2^n, n\le0^{[1]}$$.  
The notation $$u_1^N$$ as shorthand for denoting a row vector $$(u_1, \dots , u_N)$$.  
The vector channel **$$W_N$$** is the virtual channel between the input sequence $$u_1^N$$ to a linear encoder and the output sequence $$y^N_1$$ of $$N$$ copies of the original channel $$W$$. $$W_1 = W$$ is one copy of $$W$$.  
We use $$W^N : {\cal X}^N \to {\cal Y}^N$$ to denote the vector channel between the input sequence $$x_1^N$$ and the output sequence $$y_1^N$$ of $$N$$ copies of the original channel $$W$$.  
![w2]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201810/w2.png){:.aligncenter}   
<center>$$W_N(y_1^N|u_1^N) = W^N(y_1^N|u_1^NG_N) = W^N(y_1^N|x_1^N) = \sum_{i=1}^N W(y_i|x_i)$$</center>  
for any $$N = 2^n, n \le 0$$,  
<center>$$G_N = B_N F^{\otimes n}$$</center>  
where $$B_N$$ is a permutation matrix known as **bit-reversal**, $$F \triangleq \left[\begin{smallmatrix}1 & 0\cr 1 & 1 \end{smallmatrix}\right]$$ and $$\otimes n$$ is **Kronecker power**, which is a **Hadamard transform**.  
The *bit-reversal* is shown as below from$$^{[8]}$$  
![bitreversal]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201810/bitreversal.png){:.aligncenter}   
Sort a data sequence in nomal order by successive examination of the MSB as the left in the picture.  
Sort the sequence $$x[n]$$ as the permutation matrix(sequence A030109 in the OEIS) order, such a separation of odd and even can be carried out by examining the LSB.  
The recursive construction of $$W_N$$ from two copies of $$W_{N/2}$$ is useful for software and hardware$$^{[9]}$$. But for hardware implementation, the "rewire" structure is more attractive:  
![rewire]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201810/rewire.png){:.aligncenter}  
We denote random variables (RVs) by upper-case letters, the coding scheme for $$U_1,U_2 \, \overset{i.i.d.}{\sim} \, Unif\{0,1\}$$.  
It is easy to see that $$U_1, U_2$$ and $$X_1, X_2$$ have a **bijection**, and further coupling this with the fact $$X_1,X_2 \, \overset{i.i.d.}{\sim} \, Unif\{0,1\}$$. We have  
<center>$$I(U_1,U_2;Y_1,Y_2) = I(X_1,X_2;Y_1,Y_2) = 2C = 2I(W)$$</center>  
and for $$U_1, \dots, U_N \, \overset{i.i.d.}{\sim} \, Unif\{0,1\}$$, then $$X_1, \dots, X_N \, \overset{i.i.d.}{\sim} \, Unif\{0,1\}$$   
<center>$$\eqalign{I(U^N;Y^N) &= I(X^N;Y^N) \\&= H(Y^N) - H(Y^N|X^N) \\&= H(Y^N) - \sum_{i=1}^N H(Y_i|Y_1, ... , Y_{i-1}, X^N) \\&= \sum_{i=1}^N H(Y_i) - \sum_{i=1}^N H(Y_i|X_i) \\&= \sum_{i=1}^N I(X_i;Y_i) \\&= NI(W)}$$</center>  
#### **Channel Splitting**  
Channel Splitting is to split $$W_N$$ back into a set of $$N$$ binary-input coordinate channels $$W^{(i)}_N : X \to {\cal Y}^N \times {\cal X}^{i−1}, 1 \le i \le N$$.  
The transition probability of the $$W_N^{(i)}$$ is defined as$$^{[1]}$$  
<center>$$W_N(u_1^N;y_1^N) = \sum_{i=1}^N W_N^{(i)}(u_i;y_1^Nu_1^{i-1})$$</center>  
For the $$u_i$$ is $$i.i.d. , I(u_i;u_1^{i-1}) = 0$$,  
<center>$$\begin{align} I(u_1^N;y_1^N) &= \sum_{i=1}^N I(u_i;y_1^N|u_1^{i-1}) \tag{Chain rule for information} \\ &= \sum_{i=1}^N \{I(u_i;y_1^N,u_1^{i-1}) - I(u_i;u_1^{i-1})\} \tag{Chain rule for mutual information} \\ &= \sum_{i=1}^N I(u_i;y_1^Nu_1^{i-1}) \end{align}$$</center>  
![splitting]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201810/splitting.png){:.aligncenter}  
The transition probabilities are given by  
<center>$$\begin{align} W_N^{(i)} (y_1^N,u_1^{i-1}|u_i) &= {P(y_1^N,u_1^{i-1}) \over P(u_i)} \\&= {P(y_1^N,u_1^i) \over P(u_i)} \tag{i.i.d.} \\&= \sum_{u_{i+1}^N \in {\cal X}^{N-i}} {P(y_1^N,u_1^i,u_{i+1}^N) \over P(u_i)} \tag{$p_X(x) = \sum_y P_{X,Y}(x,y)$} \\&= \sum_{u_{i+1}^N \in {\cal X}^{N-i}} {P(y_1^N|u_1^N)P(u_1^N) \over P(u_i)} \\&= \sum_{u_{i+1}^N \in {\cal X}^{N-i}} P(y_1^N|u_1^N) {2^{-N} \over 2^{-1}} \\&= \sum_{u_{i+1}^N \in {\cal X}^{N-i}} {1 \over 2^{N-1}} W_N(y_1^N|u_1^N) \tag{*} \\&= \sum_{u_{i+1}^N \in {\cal X}^{N-i}} {1 \over 2^{N-1}} W^N(y_1^N|x_1^N) \\&= \sum_{u_{i+1}^N \in {\cal X}^{N-i}} {1 \over 2^{N-1}} W(y_1|x_1)W(y_2|x_2) \dots W(y_N|x_N) \end{align}$$</center>  
For $$N=2$$,  
<center>$$\begin{align} W_2^{(1)}(y_1^2|u_1) &= \sum_{u_2^2 \in {\cal X}^1} {1 \over {2^{2-1}}}W(y_1|x_1)W(y_2|x_2) \tag{$i=1$, get rid of $u_1^0$} \\&= \sum_{u_2} {1\over 2}W(y_1|u_1\oplus u_2)W(y_2|u_2) \end{align}$$</center>  
<center>$$\begin{align} W_2^{(2)}(y_1^2,u_1|u_2) &=  {1 \over 2}W(y_1|x_1)W(y_2|x_2) \tag{$i=2$, get rid of ${\cal X}^0$} \\&= {1\over 2}W(y_1|u_1\oplus u_2)W(y_2|u_2) \end{align}$$</center>  
This is from$$^{[1]}$$  
<center>$$\begin{align} W_{2N}^{(2i-1)}(y_1^{2N},u_1^{2i-2}|u_{2i-1}) &=  \sum_{u_{2i}^{2N}} {1\over 2^{2N-1}}W_{2N}(y_1^{2N}|u_1^{2N}) \\&= \sum_{u_{2i,o}^{2N},u_{2i,e}^{2N}} {1\over 2^{2N-1}}W_N(y_1^N|u_{1,o}^{2N}\oplus u_{1,e}^{2N})W_N(y_{N+1}^{2N}|u_{1,e}^{2N}) \\&= \sum_{u_{2i}} {1\over 2} \sum_{u_{2i+1,e}^{2N}} {1\over 2^{N-1}} W_N(y_{N+1}^{2N}|u_{1,e}^{2N})\sum_{u_{2i+1,o}^{2N}} {1\over 2^{N-1}} W_N(y_1^N|u_{1,o}^{2N} \oplus u_{1,e}^{2N}) \end{align}$$</center>  
because, as both $$u_{2i+1,o}^{2N}$$ and $$u_{2i+1,o}^{2N} \oplus u_{2i+1,e}^{2N}$$ range over $$\cal X^{N−i}$$. and from (*),  
<center>$$\begin{align} sum_{u_{2i+1,o}^{2N}} {1\over 2^{N-1}} W_N(y_1^N|u_{1,o}^{2N} &= \end{align}$$</center>
  
Reference:  
1. E. Arikan. *Channel polarization: A method for constructing capacity-achieving codes for symmetric binary-input memoryless channels*. IEEE Trans. on Information Theory, vol.55, no.7, pp.3051–3073, July 2009.  
2. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
3. David J.C. MacKay. (2003). *Information Theory, Inference, and Learning Algorithms*. Cambridge University Press.  
4. Erdal Arıkan. (2011.8.1). *Polar Coding Status and Prospects*. The IEEE International Symposium on Information Theory. ISIT’2011 Saint Petersburg, Russia.  
5. R. Pedarsani, S. H. Hassani, I. Tal, and E. Telatar. *On the Construction of Polar Codes*. Proceedings of IEEE International Symposium on Information Theory, Saint Petersburg, Jul. 2011.  
6. Eren Sasoglu. *Polarization and Polar Codes*. Foundations and Trends in Communications and Information Theory Vol. 8, No. 4 (2011) 259–381
7. David Tse. *EE376A/Stats376A: Information Theory*. Winter 2016-2017. https://www.stanford.edu/  
8. Alan V. Oppenheim. Ronald W. Schafer. *Discrete-Time Signal Processing, 2nd*. Prentice Hall. 1999.  
9. E. Arikan. *Polar codes: A pipelined implementation*. 4th International Symposium on Broadband Communication (ISBC 2010) July 11-14, 2010, Melaka, Malaysia  
10. Vincent Y. F. Tan. *EE5139R: Information Theory for Communication Systems:2016/7, Semester 1*. https://www.ece.nus.edu.sg/  

