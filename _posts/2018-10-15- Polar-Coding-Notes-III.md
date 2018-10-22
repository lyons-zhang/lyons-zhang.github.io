---
title:   Polar Coding Notes III
description: 
categories: Digital Comunication
---

>  For any B-DMC $$W$$, the channels $$\{W_N^{(i)}\}$$ polarize in the sense that, for any fixed $$\delta \in (0, 1)$$, as $$N$$ goes to infinity through powers of two, the fraction of indices $$i \in \{1, \dots, N\}$$ for which $$I(W_N^{(i)}) \in (1 − \delta, 1]$$ goes to $$I(W)$$ and the fraction for which $$I(W_N^{(i)}) \in [0, \delta)$$ goes to $$1−I(W)^{[1]}$$.
  
#### **Mrs. Gerber’s Lemma**  
Mrs. Gerber’s Lemma provides a lower bound on the entropy of the modulo-2 sum of two binary random vectors$$^{[3]}$$.  
Let $$H^{-1} : [0, 1] \to [0, 1/2]$$ be the inverse of the binary entropy function.  
Scalar MGL: Let $$X$$ be a binary random variable and let $$U$$ be an arbitrary random variable. If $$Z \sim Bern(p)$$ is independent of $$(X, U)$$ and $$Y = X \oplus Z$$, then
<center>$$H(Y|U) \le H(H^{−1}(h(X|U)) \ast p)$$</center> 
Vector MGL: Let $$X^n$$ be a binary random vector and $$U$$ be an arbitrary random variable. If $$Z^n$$ is a vector of independent and identically distributed $$Bern(p)$$ random variables independent of $$(X^n, U)$$ and $$Y^n = X^n \oplus Z^n$$, then  
<center>$${H(Y^n|U) \over n} \le H(H^{−1}({H(X^n|U) \over n})) \ast p)$$</center>  
The convolution of $$p$$ and $$x$$ is denoted by  
<center>$$p \ast x := p(1 − x) + (1 − p)x$$</center>  


#### **Channel Splitting**  

Reference:  
1. E. Arikan. *Channel polarization: A method for constructing capacity-achieving codes for symmetric binary-input memoryless channels*. IEEE Trans. on Information Theory, vol.55, no.7, pp.3051–3073, July 2009.  
2. A. D. Wyner and J. Ziv. *A theorem on the entropy of certain binary sequences and applications (Part I)*. IEEE Trans. Inform. Theory, vol.19, no.6, pp. 769-772, Nov. 1973.  
3. Abbas El Gamal and Young-Han Kim. *Network Information Theory*. Cambridge University Press. 2011.  



