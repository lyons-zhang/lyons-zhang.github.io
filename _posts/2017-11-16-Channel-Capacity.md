---
title: Channel Capacity
description: Binary Symmetric Channel, Binary Erasure Channel, Symmetric Channels, Feedback Capacity 
categories: Information Theory
---

>  The characterization of the channel capacity (the logarithm of the number of distinguishable signals) as the maximum mutual information is the central and most famous success of information theory.   
  
### **Reading**    
The textbook is Chapter 7 of "Elements of Information Theory"[ref 1].
[Channel Capacity]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201711/Channel Capacity.pdf){:.aligncenter}   
[Channel Capacity]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201711/信道容量.pdf){:.aligncenter}   
### **Supplementary**  
##### **symmetric channel **
A **permutation** (rearrangement) of a list is a list that contains each of the number exactly once, e.g., $$(2,4,3,5,1) \in perm 5$$.   
All the rows and columns of symmetric channel transition matrix subject to the constraint $$\sum p_{i,j} = 1$$.   
##### **Capacity of Binary Erasure Channel**  
$$\eqalign{ H(Y|X) &= -\sum\limits_x P(X=x) \sum\limits_y P(Y|X=x)logP(Y|X=x) \cr &= -\sum\limits_x P(X=x)[\alpha log\alpha+(1−\alpha)log(1−\alpha)+0] \cr &= H(\alpha)}$$   
$$P(Y=0) = \pi(1−\alpha)$$   
$$P(Y=1) = (1−\pi)(1−\alpha)$$   
$$P(Y=lost) = \pi \alpha + (1 - \pi)\alpha = \alpha$$   
Thus,   
$$\eqalign { H(Y) &=  -\pi (1 - \alpha) log(\pi (1 - \alpha)) - (1 - \pi) (1 - \alpha) log((1 - \pi) (1 - \alpha)) - \alpha log \alpha \cr &= (1 - \alpha) h(\pi) + h(\alpha) }$$   
Since $$P(Y = lost)$$ is independent of $$\pi$$, $$H(Y)$$ is maximum for $$\pi = 0.5$$, Eventually, the maximum of $$H(Y)$$ is $$(1−\alpha)+H(\alpha)$$, at last we find $$C = 1-\alpha$$.   
##### **Empirical Entropy**  
Let $$\hat p$$ denote the empirical probability mass function corresponding to $$X_1, X_2, \ldots , X_n i.i.d. \~ p(x), x \in \mathcal{X}$$. Specifically,    
$$\hat p(x) = \frac{1}{n}|\{ i \mid x_i = x\}| = \frac{1}{n} \sum_{i=1}^n \delta_x(x_i)$$    
$$\eqalign { H(\hat{p}) &= - \sum_{x \in \mathcal{X}} \hat{p}(x) \log \hat{p}(x) &= - \sum_{x \in \mathcal{X}} \frac{1}{n} \sum_{i=1}^n \delta_x(x_i) \log \hat{p}(x) &= -\frac{1}{n} \sum_{i=1}^n \log\hat{p}(x_i) }$$    
From this we see that,   
$$H(\hat{p}) = - \frac{1}{n} \log \hat{p}(x^n) ~~~~~ \hat{p}(x^n) = \prod_{i=1}^n \hat{p}(x_i)$$   

    
Reference:  
1. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
