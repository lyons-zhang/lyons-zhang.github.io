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
##### **Binary Erasure Channel**
$$\eqalign { H(Y|X) = −\sum\limits_x P(X=x) \sum\limits_y P(Y|X=x)logP(Y|X=x) \cr &= −\sum\limits_x P(X=x)[\alpha log\alpha+(1−\alpha)log(1−\alpha)+0] \cr &= H(\alpha)$$   

    
    
Reference:  
1. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
