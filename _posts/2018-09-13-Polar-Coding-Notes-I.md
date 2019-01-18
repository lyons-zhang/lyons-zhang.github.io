---
title:   Polar Coding Notes I
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
<center>$$\eqalign{ C &= \max_{p_X(x)} I(X;Y) \\ &= \max_{p_X(x)} \sum_{x \in \cal X}\sum_{y \in \cal Y} p_{X,Y}(x,y) \log_2 {p_{Y|X}(y|x) \over p_Y(y)} \\ &= \max_{p_X(x)} \sum_{x \in \cal X}\sum_{y \in \cal Y} p_X(x)p_{Y|X}(y|x) \log_2 {p_{Y|X}(y|x) \over p_Y(y)} }$$</center>
A *symmetric binary discrete memoryless channel* (B-DMC) is a B-DMC $$W : {0,1} \to \cal Y$$ with the additional property that there exists a *permutation* over the outputs of the channel $$\pi : \cal Y \to \cal Y$$ such that $$\pi = \pi^{-1}$$ and $$W(y|0) = W(\pi(y)|1)$$.  
In the symmetric B-DMC, the two inputs have the same probability **$$p(x) = 1/2$$**, the **symmetric capacity** can be calculated as:  
<center>$$\eqalign{ I(W) &= I(X;Y) \\ &= \sum_{y \in \cal Y}\sum_{x \in \cal X} {p_{X,Y}(x,y) \over p_X(x)}p_X(x) \log_2 {p_{X,Y}(x,y) \over p_X(x)} {1 \over p_Y(y)} \\ &= \sum_{y \in \cal Y}\sum_{x \in \cal X} {p_{Y|X}(y|x)p_X(x)} \log_2 {p_{Y|X}(y|x) \over p_Y(y)} \\&= \sum_{y \in \cal Y}\sum_{x \in \cal X} {1 \over 2}p_{Y|X}(y|x) \log_2 { p_{Y|X}(y|x) \over {\sum_{x' \in \cal X} p_X(x') p_{Y|X}(y|x')}} \\&= \sum_{y \in \cal Y}\sum_{x \in \cal X} {1 \over 2}W(y|x) \log { W(y|x) \over { {1 \over 2}W(y|0) + {1 \over 2}W(y|1)} } }$$</center>  
Where $$x'$$ is a **dummy(bound) variable**, we can ignore the difference here. Here we use two important formula:  
<center>$$p_{X,Y}(x,y) = p_X(x)p_{Y|X}(y|x) = p_Y(y)p_{X|Y}(x|y)$$</center>
<center>$$p_X(x) = \sum_y p_{X,Y}(x,y) = \sum_y p_Y(y) p_{X|Y}(x|y)$$</center>
Use base-2 logarithms,  
<center>$$0 \le I(W) = I(X;Y) \le H(x) \le \log{|\cal X|} = 1$$</center>
#### **Bhattacharyya parameter**  
Let a binary code have blocklength $$N$$ and just two codewords, which differ in $$d$$ places. For simplicity, let’s assume $$d$$ is even.   
What is the error probability if this code is used on a binary symmetric channel with probability of error $$\epsilon$$.   
Bit flips matter only in places where the two codewords differ. The error probability is dominated by the probability that $$d/2$$ of these bits are flipped. What happens to the other bits is irrelevant, since the optimal decoder ignores them$$^{[2]}$$.   
<center>$$P(\text{block error}) \approx \dbinom{d}{d/2} \epsilon^{d/2}(1-\epsilon)^{d/2} \;\;\; (\bf{\text{binomial distribution}})$$</center>   
From **Stirling’s approximation**,   
<center>$$x! \approx x^x e^{-x} \;\;\; \Rightarrow \;\;\; \dbinom{N}{r} \approx 2^{NH_b(r/N)}$$</center>   
So,   
<center>$$P(\text{block error}) \approx {[\epsilon^{1/2}(1-\epsilon)^{1/2}]}^d \equiv {[\beta(\epsilon)]}^d$$</center>  
where $$\beta(\epsilon) = 2\epsilon^{1/2}(1 − \epsilon)^{1/2}$$ is called the **Bhattacharyya parameter** of the channel. Arıkan calls $$Z(W)$$ the *Bhattacharyya parameter*$$^{[5]}$$  
<center>$$Z(W) = \sum_{y \in \cal Y} \sqrt{W(y|0)W(y|1)}$$</center>  
For a BSC with probability of error $$\epsilon$$,  
<center>$$Z_{BSC}(W) = \sqrt{W(0|0)W(0|1)} + \sqrt{W(1|0)W(1|1)} = 2\sqrt{\epsilon(1-\epsilon)}$$</center>  
For a BEC with probability of error $$\epsilon$$,  
<center>$$Z_{BEC}(W) = \sqrt{W(0|0)W(0|1)} + \sqrt{W(1|0)W(1|1)} + \sqrt{W(Err|0)W(Err|1)} = \epsilon$$</center>  
![Bhattacharyya]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201809/Bhattacharyya.svg){:.aligncenter}  
**Distance isn’t everything!**  
Now, consider a general linear code with distance $$d$$. Its block error probability must at least than $$\dbinom{d}{d/2} \epsilon^{d/2}(1-\epsilon)^{d/2}$$, independent of the blocklength $$N$$ of the code.   
For this reason, a sequence of codes of increasing blocklength $$N$$ and constant distance $$d$$ (i.e., ‘very bad’ distance) cannot have a block error probability that tends to zero, on any binary symmetric channel.  
The *Bhattacharyya measure* (Bhattacharyya, 1943) (or coefficient) is a divergence-type measure between distributions, defined as,   
<center>$$\beta(p,p') = \sum_{i=1}^N \sqrt{p(i)p'(i)}$$</center>   
where $$p(i)$$ and $$p'(i)$$ represent probability distributions, $$\sum_{i=1}^N p(i) = \sum_{i=1}^N p'(i) = 1$$.  
Any symmetric B-DMC can be represented as a collection of binary symmetric channels (BSC’s)$$^{[4]}$$. The binary input is given to one of these BSC’s at random such that the $$i$$-th BSC is chosen with probability $$p_i$$. The output of this BSC together with its cross over probability $$x_i$$ is considered as the output of the channel. Therefore, a discrete BMS channel $$W$$ can be completely described by a random variable $$\cal X \in [0, {1 \over 2}]$$. The *pdf* of $$\cal X$$ will be of the form:  
<center>$$P_{\cal X}(x) = \sum_{i=1}^m p_i \delta(x - x_i)$$</center>
Such that $$\sum_{i=1}^m p_i = 1$$ and $$0 \le x_i \le 1/2$$. Note that $$Z(W)$$ and $$1 − I(W)$$ are expectations of the functions $$f(x) = 2\sqrt{x(1 − x)}$$ and $$g(x) = −x \log(x) − (1 − x)\log(1 − x)$$ over the distribution $$P_{\cal X}$$, respectively.  
It is well-known that the Bhattacharyya parameter **upper bounds the error probability of the optimal decision rule**, and therefore may be used as **a measure of reliability**.  

Reference:  
1. Thomas M. Cover, Joy A. Thomas. (2006). *Elements of Information Theory*. John Wiley & Sons. 
2. David J.C. MacKay. (2003). *Information Theory, Inference, and Learning Algorithms*. Cambridge University Press.  
3. Erdal Arıkan. (2011.8.1). *Polar Coding Status and Prospects*. The IEEE International Symposium on Information Theory. ISIT’2011 Saint Petersburg, Russia.  
4. R. Pedarsani, S. H. Hassani, I. Tal, and E. Telatar. *On the Construction of Polar Codes*. Proceedings of IEEE International Symposium on Information Theory, Saint Petersburg, Jul. 2011.  
5. E. Arikan. *Channel polarization: A method for constructing capacity-achieving codes for symmetric binary-input memoryless channels*. IEEE Trans. on Information Theory, vol.55, no.7, pp.3051–3073, July 2009.  
6. Eren Sasoglu. *Polarization and Polar Codes*. Foundations and Trends in Communications and Information Theory Vol. 8, No. 4 (2011) 259–381