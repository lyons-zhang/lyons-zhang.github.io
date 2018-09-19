---
title:   Polar Coding Notes
description: 
categories: Digital Comunication
---

>  With the development of polar codes in 2008 by Erdal Arıkan, the search of computationally efficient capacity achieving codes came to an end, as these codes achieve capacity while having encoding and decoding complexities of $$O(n \log n)$$, where $$n$$ is the block length.
  

#### **The channel**    
Let $$W : X \to Y$$ be a binary-input discrete memoryless channel   
![channel]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201809/channel.svg){:.alignleft}   
   
 - Input alphabet: $$\cal X = \{0, 1\}$$  
 - Output alphabet: $$\cal Y$$  
 - Transition probabilities: $$W(y|x), x \in {\cal X}, y \in {\cal Y}$$   
    
     
##### **Bhattacharyya parameter**  
Let a binary code have blocklength $$N$$ and just two codewords, which differ in $$d$$ places. For simplicity, let’s assume $$d$$ is even.   
What is the error probability if this code is used on a binary symmetric channel with probability of error $$f$$.   
Bit flips matter only in places where the two codewords differ. The error probability is dominated by the probability that $$d/2$$ of these bits are flipped. What happens to the other bits is irrelevant, since the optimal decoder ignores them.   
<center>$$P(\text{block error}) \approx \dbinom{d}{d/2} f^{d/2}(1-f)^{d/2} \;\;\; (*\text{binomial distribution}*)$$</center>   
From **Stirling’s approximation**,   
<center>$$x! \approx x^x e^{-x} \;\;\; \Rightarrow \;\;\; \dbinom{N}{r} \approx 2^{NH_b(r/N)}$$</center>   
So,   
<center>$$P(\text{block error}) \approx {[f^{1/2}(1-f)^{1/2}]}^d \equiv {[\beta(f)]}^d$$</center>  
where $$\beta(f) = 2f^{1/2}(1 − f)^{1/2} is called the *Bhattacharyya parameter* of the channel.   
The *Bhattacharyya measure* (Bhattacharyya, 1943) (or coefficient) is a divergence-type measure between distributions, defined as,   
<center>$$\beta(p,p') = \sum_{i=1}^N \sqrt {p(i)p'(i)}$$</center>   
where $$p(i)$$ and $$p'(i)$$ represent probability distributions, $$\sum_{i=1}^N p(i) = \sum_{i=1}^N p'(i) = 1$$.   
Now, consider a general linear code with distance $$d$$. Its block error probability must at least than $$\dbinom{d}{d/2} f^{d/2}(1-f)^{d/2}$$, independent of the blocklength $$N$$ of the code.   
For this reason, a sequence of codes of increasing blocklength $$N$$ and constant distance $$d$$ (i.e., ‘very bad’ distance) cannot have a block error probability that tends to zero, on any binary symmetric channel.   




Reference:  
1. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
2. David J.C. MacKay. (2003). *Information Theory, Inference, and Learning Algorithms*. Cambridge University Press.