---
title: Vector Space and Inner Product Space
description: Vector space, Inner product space, Gram-Schmidt orthonormalization
categories: Digital Communication
---

>  Linear algebra is the study of linear maps on finite-dimensional vector spaces. Use of vectors to represent a countably infinite sequence is a small conceptual extension. Viewing waveforms as vectors is a larger conceptual extension. We have to view vectors as abstract objects rather than as n-tuples. Orthogonal expansions are best viewed in vector space terms.  

### **Vector space**  
A *vector space* $$\mathcal V$$ is a set of elements, $$\vec v \in \mathcal V$$, called vectors, along with a set of rules for operating on both these vectors and a set of ancillary elements called scalars.   
A vector space with real scalars is called a *real vector space*, and one with complex scalars is called a *complex vector space*.   
#### **Axioms of vector space**  
##### **Addition**   
For each $$\vec v \in \mathcal V$$ and $$\vec u \in \mathcal V$$, there is a vector $$\vec v + \vec u \in \mathcal V$$ called the sum of $$\vec v$$ and $$\vec u$$ satisfying:   
* Commutativity: $$\vec v + \vec u = \vec u + \vec v$$.
* Associativity: $$\vec v + (\vec u + \vec w) = (\vec v + \vec u) + \vec w$$, for each $$\vec v, \vec u, \vec w \in \mathcal V$$.
* Zero: there is a unique vector $$0 \in \mathcal V$$ such that $$\vec v + 0 = \vec v$$ for all $$\vec v \in \mathcal V$$.
* Negation: for each $$\vec v \in \mathcal V$$, there is a unique vector $$−\vec v$$ such that $$\vec v + (− \vec v) = 0$$.   

##### **Scalar multiplication**   
For each scalar $$\alpha$$ and each $$\vec v \in \mathcal V$$ there is a unique vector $$\alpha \vec v \in \mathcal V$$ called the scalar product of $$\alpha$$ and $$\vec v$$ satisfying:   
* Scalar associativity:	$$\alpha (\beta \vec v) = (\alpha \beta)\vec v$$ for all scalars $$\alpha,\beta$$, and all $$\vec v \in \mathcal V$$.
* Unit multiplication: for the unit scalar 1, $$1\vec v = \vec v$$ for all $$\vec v \in \mathcal V$$.   

##### **Distributive laws**   
* For all scalars $$\alpha$$ and all $$\vec v, \vec u \in \mathcal V$$, $$\alpha (\vec v + \vec u) = \alpha \vec v + \alpha \vec u$$.
* For all scalars $$\alpha, \beta$$ and all $$\vec v \in \mathcal V$$, $$(\alpha + \beta)\vec v = \alpha \vec v + \beta \vec v$$.   

#### **Finite-dimensional vector spaces**   
The set of finite-energy complex waveforms can be viewed as a complex vector space. For space $$L^2$$ of finite energy complex functions, we can define $$\vec u + \vec v$$ as function $$\vec w$$ where $$w(t) = u(t) + v(t)$$ for each t. Define $$\alpha \vec v$$ as vector $$\vec u$$ for which $$u(t) = \alpha v(t)$$.   
* **Span**: A set of vectors $$\vec {v_1}, \vec {v_2}, ..., \vec {v_n} \in \mathcal V$$ spans $$\mathcal V$$ (and is called a *spanning set* of $$\mathcal V$$) if every vector $$\vec v \in \mathcal V$$ is a linear combination of $$\vec {v_1}, \vec {v_2}, ..., \vec {v_n}$$.   
* **Finite-dimensional**: A vector space $$\mathcal V$$ is finite-dimensional if a finite set of vectors $$\vec {v_1}, \vec {v_2}, ..., \vec {v_n}$$ exist that span $$\mathcal V$$.   
* **Linearly dependent**: A set of vectors $$\vec {v_1}, \vec {v_2}, ..., \vec {v_n} \in \mathcal V$$ is linearly dependent if $$sum_{j=1}^n \alpha_j\vec {v_j}$$ for some set of scalars not all equal to 0. This implies that each vector $$\vec {v_k}$$ for which $$\alpha_k \ne 0$$ is a linear combination of the others.   
* **Basis**: A set of vectors $$\vec {v_1}, \vec {v_2}, ..., \vec {v_n} \in \mathcal V$$ is defined to be a basis for $$\mathcal V$$ if the set both spans $$\mathcal V$$ and is linearly independent. The **dimension** of a finite-dimensional vector space is defined as the number of vectors in a basis.   

### **Inner product spaces**
Vector space definition lacks distance and angles. Inner product adds these features. The inner product of $$\vec v$$ and $$\vec u$$ is denoted $$<\vec v, \vec u>$$.   
#### **Axioms of inner product space**   
* Hermitian symmetry: $$<\vec v, \vec u> = <\vec u, \vec v>^*$$   
* Hermitian bilinearity: $$<\alpha\vec v + \beta \vec u, \vec w> = \alpha <\vec v, \vec w> + \beta <\vec u, \vec w>$$
                         $$<\vec v, \alpha \vec u + \beta \vec w> = \alpha^* <\vec v, \vec u> + \beta^*<\vec v, \vec w>$$  
* Strict positivity:  $$<\vec v, \vec v> \ge 0$$, equality iff $$\vec v = \vec 0$$.   



Reference:  
1. Robert Gallager. (2006). *6.450 Digital Communication*. MIT OpenCourseWare (http://ocw.mit.edu/) 
2. Robert G.Gallager. (2009). *Principles of Digital Communication* (New York: Cambridge University Press).  

