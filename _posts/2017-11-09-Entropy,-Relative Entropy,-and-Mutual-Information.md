---
title: Entropy, Relative Entropy, and Mutual Information
description: Entropy, Relative Entropy, Mutual Information
categories: Information Theory
---

>  For any probability distribution, we define a quantity called the **entropy**, which has many properties that agree with the intuitive notion of what a measure of information should be. **Mutual information** is a measure of the amount of information one random variable contains about another. Entropy then becomes the **self-information** of a random variable. Mutual information is a special case of a more general quantity called **relative entropy**, which is a measure of the distance between two probability distributions.  
  
### **Reading and Supplementary**    
The textbook is Chapter 2 of "Elements of Information Theory"[ref 1].   

[Entropy, Relative Entropy, and Mutual Information]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201711/Entropy, Relative Entropy, and Mutual Information.pdf){:.aligncenter}    
[熵, 相对熵和互信息]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201711/熵、相对熵与互信息.pdf){:.aligncenter}   
      
##### **Chain rule**  
$$\eqalign { H(X, Y|Z) &= -\sum_{x \in \mathcal{X}}\sum_{y \in \mathcal{Y}}\sum_{z \in \mathcal{Z}} p(x,y,z) \log p(x,y|z) \cr 
&= -\sum_{x \in \mathcal{X}}\sum_{y \in \mathcal{Y}}\sum_{z \in \mathcal{Z}} p(x,y,z) \log p(x|z) - \sum_{x \in \mathcal{X}}\sum_{y \in \mathcal{Y}}\sum_{z \in \mathcal{Z}} p(x,y,z) \log p(y|x,z) \cr 
&= - \sum_{x \in \mathcal{X}}\sum_{z \in \mathcal{Z}} p(x,z) \log p(x|z) - \sum_{x \in \mathcal{X}}\sum_{y \in \mathcal{Y}}\sum_{z \in \mathcal{Z}} p(x,y,z) \log p(y|x,z) \cr 
&= H(X|Z) + H(Y|X,Z) }$$   
$$P(X,Y|Z) = \frac{P(X,Y,Z)}{P(Z)}$$   
$$P(Y|X,Z) = \frac{P(X,Y,Z)}{P(X,Z)}$$   
$$P(X|Z) = \frac{P(X,Z)}{P(Z)}$$   
$$P(X,Y|Z) = \frac{P(X,Y,Z)}{P(Z)} = \frac{P(X,Y,Z)}{P(X,Z)}\frac{P(X,Z)}{P(Z)} = P(Y|X,Z) P(X|Z)$$   
$$H(X_1, X_2, ... , Xn) = H(X_1) + \sum\limits_{i=2}^n H(X_i | X_{i-1}, ... , X_1)$$   
   
##### **Chain Rule for Conditional Entropy**  
$$\eqalign { H(X_1, X_2, ... , X_n | Y) &= H(X_1, X_2, ... , X_n, Y) − H(Y) \cr &= H((X_1, Y), X_2, ... , X_n) − H(Y) \cr &= H(X_1, Y) +\sum\limits_{i=2}^n H(X_i|X_1, ... ,X_{i−1}, Y) − H(Y) \cr &= H(X_1|Y) + \sum\limits_{i=2}^n H(X_i|X_1, ... ,X_{i−1}, Y) \cr &= \sum\limits_{i=1}^n H(X_i|X_1, ... ,X_{i−1}, Y) }$$   
    
##### **Fano's inequality**   
Binary entropy function: $$H(p) = −plog_2p − (1−p)log_2(1−p)$$   
$$H(P_e)$$ in the 2.10 of [ref 1] is usually written as   
$$H(P_e) = H_b(P_e) = -P_e log(P_e) - (1-P_e) log(1-P_e)$$
    
### **Information Measures: Entropy**  
A concept generalizing the smallest expected number of input bits per symbol to an encoder, $$b$$, is the entropy.   
The entropy of a random variable(rv) can be interpreted as the "information content", a measure of its "randomness" or "uncertainty".   
It can be easily shown that a discrete uniform distribution has the largest entropy. For instance, a uniform distribution on 4 discrete values has entropy $$H(X) = 2$$ *bits/symbol*, this is the same as $$b$$ for 4-level PAM.   
The **differential entropy** of an analog rv can be negative and depends on the scaling of the outcomes.   
The distribution with maximum differential entropy for a fixed variance $$\sigma^2$$ is *Gaussian*.   
#### **Conditional Entropy**   
The definition of **conditional entropy** $$H(Y|X)$$ is valid because conditioning $$Y$$ on $$X$$ moves us into a different probability space.   
Remember that for any arbitrary function, $$E[f(X,Y)] = \sum_{x,y}p(x,y)f(x,y)$$, so probability distributions of conditional entropy is $$p(x,y)$$.   
$$H(Y|X)$$ is a measure of, on average, how much extra information you get by observing a second variable $$Y$$, given that you have already observed the first variable $$X$$.   
$$H(X|Y)$$ can be interpreted as the average amount of uncertainty left in $$X$$ after observing $$Y$$.   
#### **The Chain Rule for Entropy**   
Chain rules are important because we often encounter long chains of random variables, not just one or two.   
The intuitive sense is, we observe a series of events, and each of them tells us a little bit more information.   
#### **Mutual Information**  
**Mutual information** define a measure of the information that $$Y$$ provides about $$X$$ when $$Y$$ is observed, but $$X$$ is not.   
It can be intuitively understood as the information that $$Y$$ provides about $$X$$.   
$$I(X; X) = H(X)$$ meaning that $$X$$ tells us everything about itself.   
![mutual_information]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201711/mutual_information.png){:.aligncenter}   
Mutual information is a non-negative quantity. Relative entropy is non-negative but not a metric.   
    
Reference:  
1. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
