---
title:   Polar Coding Notes III
description: 
categories: Digital Comunication
---

>  For any B-DMC $$W$$, the channels $$\{W_N^{(i)}\}$$ polarize in the sense that, for any fixed $$\delta \in (0, 1)$$, as $$N$$ goes to infinity through powers of two, the fraction of indices $$i \in \{1, \dots, N\}$$ for which $$I(W_N^{(i)}) \in (1 − \delta, 1]$$ goes to $$I(W)$$ and the fraction for which $$I(W_N^{(i)}) \in [0, \delta)$$ goes to $$1−I(W)^{[1]}$$.
  
#### **Mrs. Gerber’s Lemma**  
Mrs. Gerber’s Lemma provides a lower bound on the entropy of the modulo-$$2$$ sum of two binary random vectors$$^{[2][3]}$$.  
Let $$h^{-1} : [0, 1] \to [0, 1/2]$$ be the inverse of the binary entropy function $$h(p) = -p\log p - (1-p)log(1-p)$$.  
The function $$f(u) = h(h^{-1}(u)\ast p), u \in [0,1]$$ is convex in $$u$$ for every $$p \in (0,1/2]$$.  
The convolution of $$p$$ and $$x$$ is denoted by  
<center>$$a \ast b := a(1 − b) + (1 − a)b$$</center>  
**Scalar MGL**: Let $$X$$ be a binary random variable and let $$U$$ be an arbitrary random variable. If $$Z \sim Bern(p)$$ is independent of $$(X, U)$$ and $$Y = X \oplus Z$$, then
<center>$$h(Y|U) \ge h(h^{−1}(h(X|U)) \ast p)$$</center> 
**Vector MGL**: Let $$X^n$$ be a binary random vector and $$U$$ be an arbitrary random variable. If $$Z^n$$ is a vector of independent and identically distributed $$Bern(p)$$ random variables independent of $$(X^n, U)$$ and $$Y^n = X^n \oplus Z^n$$, then  
<center>$${h(Y^n|U) \over n} \ge h(h^{−1}({h(X^n|U) \over n}) \ast p)$$</center>  
Let $$X,Y$$ are two binary random variable, from$$^{[2]}$$  
<center>$$H(X|Y) = \sum_{y\in\{0,1\}} p(Y=y)H(X|Y=y) \tag{conditional entropy definition}$$</center>  
Let  
<center>$$\beta(y) = p(X=1|Y=y)$$</center>  
Then  
<center>$$P(X=0|Y=y) = 1 - \beta(y)$$</center>  
so that  
<center>$$\begin{align} H(X|Y=y) &= \sum_{x\in\{0,1\}} p(x|y)\log p(x|y) \tag{conditional entropy definition} \\&= h(\beta(y)) \end{align}$$</center>  
and  
<center>$$H(X|Y) = \sum_{y\in\{0,1\}} p(Y=y)H(X|Y=y) = \sum_{y\in\{0,1\}} p(Y=y)h(\beta(y)) = Eh(\beta(y))$$</center>  
 

#### **Polarization for Binary-Input Channels**  



Reference:  
1. E. Arikan. *Channel polarization: A method for constructing capacity-achieving codes for symmetric binary-input memoryless channels*. IEEE Trans. on Information Theory, vol.55, no.7, pp.3051–3073, July 2009.  
2. A. D. Wyner and J. Ziv. *A theorem on the entropy of certain binary sequences and applications (Part I)*. IEEE Trans. Inform. Theory, vol.19, no.6, pp. 769-772, Nov. 1973.  
3. Abbas El Gamal and Young-Han Kim. *Network Information Theory*. Cambridge University Press. 2011.  
4. M. Alsan and I. E. Telatar. *A simple proof of polarization and polarization for non-stationary memoryless channels*. IEEE Transactions on Information Theory, 62(9):4873{4878, 2016.


