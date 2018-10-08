---
title:   Polar Coding Notes
description: 
categories: Digital Comunication
---

>  With the development of polar codes in 2008 by Erdal Arıkan, the search of computationally efficient capacity achieving codes came to an end, as these codes achieve capacity while having encoding and decoding complexities of $$O(n \log n)$$, where $$n$$ is the block length.
  

#### **The channel**    
Let $$W : X \to Y$$ be a binary-input DMC (Discrete Memoryless Channel),  
  
![channel]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201809/channel.svg){:.aligncenter}  
  
Input alphabet: $$\cal X = \{0, 1\}$$,  
Output alphabet: $$\cal Y$$,  
Transition probabilities: $$W(y|x) , x \in \cal X , y \in \cal Y$$.  
The channel capacity of a DMC (and also of other channels) is deflned as the maximal mutual information between the channel input $$X$$ and the channel output $$Y$$, maximized
with respect to the input distribution $$p_X (x)$$:  
<center>$$\eqalign{ C &= \max_{p_X(x)} I(X;Y) &= \max_{p_X(x)} \sum_{x \in \cal X}\sum_{y \in \cal Y} p_{X,Y}(x,y) \log_2 {p_{Y|X}(y|x) \over p_Y(y)} \\ &= \max_{p_X(x)} \sum_{x \in \cal X}\sum_{y \in \cal Y} p_X(x)p_{Y|X}(y|x) \log_2 {p_{Y|X}(y|x) \over p_Y(y)} }$$</center>  
###### **Symmetric B-DMC** 
A *symmetric binary discrete memoryless channel* (B-DMC) is a B-DMC $$W : {0,1} \to \cal Y$$ with the additional property that there exists a *permutation* over the outputs of the channel $$\pi : \cal Y \to \cal Y$$ such that $$\pi = \pi^{-1}$$ and $$W(y|0) = W(\pi(y)|1)$$.  
In the symmetric B-DMC, the two inputs have the same probability **$$p(x) = 1/2$$**, the symmetric capacity can be calculated as:  
<center>$$\eqalign{ I(W) &= I(X;Y) &= \sum_{y \in \cal Y}\sum_{x \in \cal X} {{p_{X,Y}(x,y)p_X(x)} \over p_X(x)}\log_2 {p_{X,Y}(x,y) \over p_X(x)} {1 \over p_Y(y)} \\ &= \sum_{y \in \cal Y}\sum_{x \in \cal X} {p_{Y|X}(y|x)p_X(x)} \log_2 {p_{Y|X}(y|x) \over p_Y(y)} \\ &= \sum_{y \in \cal Y}\sum_{x \in \cal X} {1 \over 2} p_{Y|X}(y|x) \log_2 {p_{Y|X}(y|x) \over {\sum_{x' \in \cal X}p_X(x)p_{Y|X}(y|x')}} \\ &= \sum_{y \in \cal Y}\sum_{x \in \cal X} {1 \over 2} p(y|x) \log {p(y|x) \over {{1\over 2}p(y|0)+{1\over 2}p(y|1)}}}$$</center>  
Where $$x'$$ is a **dummy(bound) variable**, but we can ignore the difference.

#### **Bhattacharyya parameter**  
Let a binary code have blocklength $$N$$ and just two codewords, which differ in $$d$$ places. For simplicity, let’s assume $$d$$ is even.   
What is the error probability if this code is used on a binary symmetric channel with probability of error $$f$$.   
Bit flips matter only in places where the two codewords differ. The error probability is dominated by the probability that $$d/2$$ of these bits are flipped. What happens to the other bits is irrelevant, since the optimal decoder ignores them.   
<center>$$P(\text{block error}) \approx \dbinom{d}{d/2} f^{d/2}(1-f)^{d/2} \;\;\; (\bf{\text{binomial distribution}})$$</center>   
From **Stirling’s approximation**,   
<center>$$x! \approx x^x e^{-x} \;\;\; \Rightarrow \;\;\; \dbinom{N}{r} \approx 2^{NH_b(r/N)}$$</center>   
So,   
<center>$$P(\text{block error}) \approx {[f^{1/2}(1-f)^{1/2}]}^d \equiv {[\beta(f)]}^d$$</center>  
where $$\beta(f) = 2f^{1/2}(1 − f)^{1/2}$$ is called the **Bhattacharyya parameter** of the channel.   
  
![Bhattacharyya]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201809/Bhattacharyya.svg){:.aligncenter}  
  
Distance isn’t everything!   
Now, consider a general linear code with distance $$d$$. Its block error probability must at least than $$\dbinom{d}{d/2} f^{d/2}(1-f)^{d/2}$$, independent of the blocklength $$N$$ of the code.   
For this reason, a sequence of codes of increasing blocklength $$N$$ and constant distance $$d$$ (i.e., ‘very bad’ distance) cannot have a block error probability that tends to zero, on any binary symmetric channel.  
  
The *Bhattacharyya measure* (Bhattacharyya, 1943) (or coefficient) is a divergence-type measure between distributions, defined as,   
<center>$$\beta(p,p') = \sum_{i=1}^N \sqrt {p(i)p'(i)}$$</center>   
where $$p(i)$$ and $$p'(i)$$ represent probability distributions, $$\sum_{i=1}^N p(i) = \sum_{i=1}^N p'(i) = 1$$. 

Reference:  
1. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
2. David J.C. MacKay. (2003). *Information Theory, Inference, and Learning Algorithms*. Cambridge University Press.  
3. Erdal Arıkan. (2011.8.1). *Polar Coding Status and Prospects*. The IEEE International Symposium on Information Theory. ISIT’2011 Saint Petersburg, Russia.  
