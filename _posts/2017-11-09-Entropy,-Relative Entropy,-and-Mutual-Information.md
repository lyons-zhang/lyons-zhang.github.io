---
title: Entropy, Relative Entropy, and Mutual Information
description: Entropy, Relative Entropy, Mutual Information
categories: Information Theorem
---

>  For any probability distribution, we define a quantity called the *entropy*, which has many properties that agree with the intuitive notion of what a measure of information should be. *Mutual information* is a measure of the amount of information one random variable contains about another. Entropy then becomes the *self-information* of a random variable. Mutual information is a special case of a more general quantity called *relative entropy*, which is a measure of the distance between two probability distributions.  
  
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
    
       
Reference:  
1. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theorem*. John Wiley & Sons. 
