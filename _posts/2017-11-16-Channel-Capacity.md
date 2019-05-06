---
title: Channel Capacity
description: Binary Symmetric Channel, Binary Erasure Channel, Symmetric Channels, Feedback Capacity 
categories: Information Theory
---

>  The characterization of the channel capacity (the logarithm of the number of distinguishable signals) as the maximum mutual information is the central and most famous success of information theory.   
  
### **Reading**    
The textbook is Chapter 7 of "Elements of Information Theory"[ref 1].   

[Channel Capacity]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201711/Channel Capacity.pdf){:.aligncenter}   
[信道容量]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201711/信道容量.pdf){:.aligncenter}   
[A Note on Symmetric Discrete Memoryless Channels]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201711/A Note on Symmetric Discrete Memoryless Channels.pdf){:.aligncenter}   
### **Supplementary**   
##### **Symmetric Channel**  
A **permutation** (rearrangement) $$\pi$$ is one-to-one and onto function   
<center>$$\pi : \{1, \ldots , n\} → \{1, \ldots , n\}$$</center>
It can be specified by the new values, e.g. $$(2,4,3,5,1)$$ specifies a permutation where $$\pi(1) = 2, \pi(2) = 4, \pi(3) = 3, \pi(4) = 5$$ and $$\pi(5) = 1$$.   
**Inverse permutation** $$\pi^{-1}$$: $$\pi \circ \pi^{-1} = id, id(i) = i, \forall i \in \{1, \ldots , n\}$$.   
There are $$n!$$ permutations of $$n$$ elements. That’s too many to generate them by numbering them all and choosing one at random. Random permutations are quite useful in randomized algorithms.   
For a symmetric channel, we have that $$H(Y|X = x) = H(r)$$ is constant for all $$x \in \mathcal{X}$$.
$$I(X;Y) = H(Y) - H(Y|X) = H(Y) − \sum_x H(Y|X = x)p(x) = H(Y)- H(r) \sum_x p(x) = H(Y) - H(r)$$.    
     
##### **Capacity of Binary Erasure Channel**  
$$\eqalign{ H(Y|X) &= -\sum\limits_x P(X=x) \sum\limits_y P(Y|X=x)logP(Y|X=x) \cr &= -\sum\limits_x P(X=x)[\alpha log\alpha+(1−\alpha)log(1−\alpha)+0] \cr &= H(\alpha)}$$   
$$P(Y=0) = \pi(1−\alpha)$$   
$$P(Y=1) = (1−\pi)(1−\alpha)$$   
$$P(Y=lost) = \pi \alpha + (1 - \pi)\alpha = \alpha$$   
Thus,   
$$\eqalign { H(Y) &=  -\pi (1 - \alpha) log(\pi (1 - \alpha)) - (1 - \pi) (1 - \alpha) log((1 - \pi) (1 - \alpha)) - \alpha log \alpha \cr &= (1 - \alpha) h(\pi) + h(\alpha) }$$   
Since $$P(Y = lost)$$ is independent of $$\pi$$, $$H(Y)$$ is maximum for $$\pi = 0.5$$, Eventually, the maximum of $$H(Y)$$ is $$(1−\alpha)+H(\alpha)$$, at last we find $$C = 1-\alpha$$.   
   
##### **Empirical Entropy**  
Let $$\hat p$$ denote the empirical probability mass function corresponding to $$X_1, X_2, \ldots , X_n {{i.i.d.} \atop \sim} p(x), x \in \mathcal{X}$$. Specifically,    
$$\hat p(x) = \frac{1}{n}|\{ i \mid x_i = x\}| = \frac{1}{n} \sum_{i=1}^n \delta_x(x_i)$$    
$$\eqalign { H(\hat{p}) &= - \sum_{x \in \mathcal{X}} \hat{p}(x) \log \hat{p}(x) &= - \sum_{x \in \mathcal{X}} \frac{1}{n} \sum_{i=1}^n \delta_x(x_i) \log \hat{p}(x) &= -\frac{1}{n} \sum_{i=1}^n \log\hat{p}(x_i) }$$    
From this we see that,   
$$H(\hat{p}) = - \frac{1}{n} \log \hat{p}(x^n) ~~~~~ \hat{p}(x^n) = \prod_{i=1}^n \hat{p}(x_i)$$  
    
##### **Jointly Typical**  
**Theorem 7.6.1**: set $${\epsilon \over 3} \le {\sigma^2 \over {n \epsilon^2}}$$ for $$n \to \infty$$.  
**7.49** is from the **7.37** directly.   
$$\begin{align} 
Pr((\tilde{X}^n, \tilde{Y}^n) \in A_{\epsilon}^{(n)}(X,Y))  \\
&= \sum\limits_{(\tilde{x}^n, \tilde{x}^n) \in A_{\epsilon}^{(n)}} p(\tilde{x}^n)p(\tilde{y}^n)  \\ 
&\le \sum\limits_{(\tilde{x}^n, \tilde{x}^n) \in A_{\epsilon}^{(n)}} 2^{(-nH(X)-\epsilon)}2^{(-nH(Y)-\epsilon)} ~~~~ \text{(from 7.35 and 7.36)}  \\
&= |A_{\epsilon}^{(n)}| 2^{(-nH(X)-\epsilon)}2^{(-nH(Y)-\epsilon)}  \\
&\le 2^{n(H(X,Y)+\epsilon)}2^{(-nH(X)-\epsilon)}2^{(-nH(Y)-\epsilon)}  \\
&= 2^{-n(I(X;Y)-3\epsilon}
\end{align}$$
   
##### **The Noisy-channel Coding Theorem**  
The *code rate* R of a channel code is the proportion of the data-stream that is useful. That is, if the code rate is $$R = \log M/n$$, for every $$\log M$$ bits of useful information, the coder generates totally $$n$$ bits of data, of which $$n-\log M$$ are redundant.  
A decoding function in 7.5: $$g : \mathcal{Y}_n \to \{1, 2, . . . , M\} \cup {fail}$$.
    
Reference:  
1. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
