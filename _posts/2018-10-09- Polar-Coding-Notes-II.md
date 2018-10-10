---
title:   Polar Coding Notes II
description: 
categories: Digital Comunication
---

>  Random codes achieve capacity but their encoding and decoding is inefficient because they do not have a 'nice structure'. Polar codes overcome this problem by splitting the channels into noiseless and useless channels. The noiseless channels preserve the encoding structure and therefore, for the information passed only over these noiseless channels, decoding can be done efficiently.
  
#### **Channel Combining**  
Channel combining is a step that combines copies of a given B-DMC $$W$$ in a recursive manner to produce a vector channel $$W_N : {\cal X}^N \to {\cal Y}^N$$, where $$N$$ can be any power of two, $$N=2^n, n\le0^{[1]}$$.  
The notation $$u_1^N$$ as shorthand for denoting a row vector $$(u_1, \dots , u_N)$$.  
The vector channel **$$W_N$$** is the virtual channel between the input sequence $$u_1^N$$ to a linear encoder and the output sequence $$y^N_1 of $$N$$ copies of the original channel $$W$$. $$W_1 = W$$ is one copy of $$W$$.  
![w2]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201810/w2.png){:.alignleft}  
The coding scheme for $$U_1,U_2 \, \overset{i.i.d.}{\sim} \, Unif\{0,1\}$$.  
It is easy to see that $$U_1, U_2$$ and $X_1, X_2$$ have a bijection, and further coupling this with the fact $$X_1,X_2 \, \overset{i.i.d.}{\sim} \, Unif\{0,1\}$$. We have  
<center>$$I(U_1,U_2;Y_1,Y_2) = I(X_1,X_2;Y_1,Y_2) = 2C = 2I(W)$$</center>




#### **Channel Splitting**  

Reference:  
1. E. Arikan. *Channel polarization: A method for constructing capacity-achieving codes for symmetric binary-input memoryless channels*. IEEE Trans. on Information Theory, vol.55, no.7, pp.3051–3073, July 2009.  
2. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
3. David J.C. MacKay. (2003). *Information Theory, Inference, and Learning Algorithms*. Cambridge University Press.  
4. Erdal Arıkan. (2011.8.1). *Polar Coding Status and Prospects*. The IEEE International Symposium on Information Theory. ISIT’2011 Saint Petersburg, Russia.  
5. R. Pedarsani, S. H. Hassani, I. Tal, and E. Telatar. *On the Construction of Polar Codes*. Proceedings of IEEE International Symposium on Information Theory, Saint Petersburg, Jul. 2011.  
6. Eren Sasoglu. *Polarization and Polar Codes*. Foundations and Trends in Communications and Information Theory Vol. 8, No. 4 (2011) 259–381
7. David Tse. *EE376A/Stats376A: Information Theory*. Winter 2016-2017. https://www.stanford.edu/