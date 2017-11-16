---
title: Entropy, Relative Entropy, and Mutual Information
description: Entropy, Relative Entropy, Mutual Information
categories: Information Theory
---

>  For any probability distribution, we define a quantity called the **entropy**, which has many properties that agree with the intuitive notion of what a measure of information should be. **Mutual information** is a measure of the amount of information one random variable contains about another. Entropy then becomes the **self-information** of a random variable. Mutual information is a special case of a more general quantity called **relative entropy**, which is a measure of the distance between two probability distributions.  
  
### **Reading**    
The textbook is Chapter 2 of "Elements of Information Theory"[ref 1].
[Entropy, Relative Entropy, and Mutual Information]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201711/Entropy, Relative Entropy, and Mutual Information.pdf){:.aligncenter}  
### **Supplementary**  
##### **Chain rule**  
$$\eqalign { H(X, Y|Z) &= -\sum_{x \in \mathcal{X}}\sum_{y \in \mathcal{Y}}\sum_{z \in \mathcal{Z}} p(x,y,z) \log p(x,y|z) \cr 
&= -\sum_{x \in \mathcal{X}}\sum_{y \in \mathcal{Y}}\sum_{z \in \mathcal{Z}} p(x,y,z) \log p(x|z) - \sum_{x \in \mathcal{X}}\sum_{y \in \mathcal{Y}}\sum_{z \in \mathcal{Z}} p(x,y,z) \log p(y|x,z) \cr 
&= - \sum_{x \in \mathcal{X}}\sum_{z \in \mathcal{Z}} p(x,z) \log p(x|z) - \sum_{x \in \mathcal{X}}\sum_{y \in \mathcal{Y}}\sum_{z \in \mathcal{Z}} p(x,y,z) \log p(y|x,z) \cr 
&= H(X|Z) + H(Y|X,Z) }$$   
   
$$P(X,Y|Z) = \frac{P(X,Y,Z)}{P(Z)} \;\;\; P(Y|X,Z) = \frac{P(X,Y,Z)}{P(X,Z)} \;\;\; P(X|Z) = \frac{P(X,Z)}{P(Z)}$$   
   
$$P(X,Y|Z) = \frac{P(X,Y,Z)}{P(Z)} = \frac{P(X,Y,Z)}{P(X,Z)}\frac{P(X,Z)}{P(Z)} = P(Y|X,Z) P(X|Z)$$   
   
$$H(X_1, X_2, ... , Xn) = H(X_1) + \sum\limits_{i=2}^n H(X_i | X_{i-1}, ... , X_1)$$   
   
Chain Rule for Conditional Entropy:   
$$\eqalign { H(X_1, X_2, ... , X_n | Y) &= H(X_1, X_2, ... , X_n, Y) − H(Y) \cr &= H((X_1, Y), X_2, ... , X_n) − H(Y) \cr &= H(X_1, Y) +\sum\limits_{i=2}^n (X_i|X_1, ... ,X_{i−1}, Y) − H(Y) \cr &= H(X_1|Y) + \sum\limits_{i=2}^n H(X_i|X_1, ... ,X_{i−1}, Y) \cr &= \sum\limits_{i=1}^n H(X_i|X_1, ... ,X_{i−1}, Y) }$$   

Fano's inequality:   
$$H(P_e)$$ in the 2.10 of [ref 1] usually write as   
$$H(P_e) = H_b(P_e) = -P_e log(P_e) - (1-P_e) log(1-P_e)$$
    
    
Reference:  
1. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
