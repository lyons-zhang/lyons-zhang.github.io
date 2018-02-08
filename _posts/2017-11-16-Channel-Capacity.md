---
title: Channel Capacity
description: Binary Symmetric Channel, Binary Erasure Channel, Symmetric Channels, Feedback Capacity 
categories: Information Theory
---

>  The characterization of the channel capacity (the logarithm of the number of distinguishable signals) as the maximum mutual information is the central and most famous success of information theory.   
  
### **Reading**    
The textbook is Chapter 7 of "Elements of Information Theory"[ref 1].
[Channel Capacity]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201711/Channel Capacity.pdf){:.aligncenter}

### **Supplementary**  
##### **Capacity of Binary Erasure Channel**  
$$\eqalign{ H(Y|X) = -\sum\limits_x P(X=x) \sum\limits_y P(Y|X=x)logP(Y|X=x) \cr &= -\sum\limits_x P(X=x)[\alpha log\alpha+(1−\alpha)log(1−\alpha)+0] \cr &= H(\alpha)}$$   
$$P(Y=0) = \pi(1−\alpha)$$   
$$P(Y=1) = (1−\pi)(1−\alpha)$$   
$$P(Y=lost) = \pi \alpha + (1 - \pi)\alpha = \alpha$$   
Thus,   
$$\eqalign { H(Y) =  -\pi (1 - \alpha) log(\pi (1 - \alpha)) - (1 - \pi) (1 - \alpha) log((1 - \pi) (1 - \alpha)) - \alpha log \alpha \cr &= (1 - \alpha) h(\pi) + h(\alpha) }$$   
Since $$P(Y = lost)$$ is independent of $$\pi$$, $$H(Y)$$ is maximum for $$\pi = 0.5$$, Eventually, the maximum of $$H(Y)$$ is $$(1−\alpha)+H(\alpha)$$, at last we find $$C = 1-\alpha$$.
    
    
Reference:  
1. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
