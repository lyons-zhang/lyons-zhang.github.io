---
title: Fourier Transforms and L2 Waveforms
description: Fourier Transform, 
categories: Digital Communication
---

>  The Fourier transform maps a function of time $$\{u(t): R \to C\}$$ into a function of frequency $$\{\hat u(f) : R \to C\}$$. The Fourier transform does not exist for all functions, and when the Fourier transform does exist, there is not necessarily an inverse Fourier transform. $$L^2$$ functions always have Fourier transforms, but only in the sense of $$L^2$$ equivalence.  

### **Fourier Transform**
The Fourier transform and its inverse are defined by  
<center>$$\hat u(f) = \int_{-\infty}^{\infty} u(t) e^{-2\pi ift} dt \;\;\;\; u(t) = \int_{-\infty}^{\infty} \hat u(f) e^{2\pi ift} df$$</center>  
The first integral exists for all $$f$$, second exists for all $$t$$.   
If we use $$\omega = 2\pi f$$, these integral become  
<center>$$\hat u(\omega) = \int_{-\infty}^{\infty} u(t) e^{-i\omega t} dt \;\;\;\; u(t) = \frac 1 {2\pi} \int_{-\infty}^{\infty} \hat u(\omega) e^{i\omega t} d\omega$$</center>   
Some book denote as $$\hat u(j\omega)$$, that's in the view of systems, for set $$s=j\omega$$ then Laplace transform becomes Fourier transform; also frequency response lives on the $$j\omega$$ axis of the Laplace transform.  
##### **Eigenfunctions**  
If the output signal $$O\{ x(t)\}$$ is a scalar $$\lambda$$ multiple of the input signal $$x(t)$$, we refer to the signal as an eigenfunction and the multiplier as the eigenvalue.  
<center>$$O\{ x(t)\} =\lambda x(t)$$</center>  
If $$x(t) = e^{st}$$ and $$h(t)$$ is the impulse response of LTI then $$O\{ e^{st}\} = (h*x)(t) = e^{st} \int_{-\infty}^{\infty} h(\tau)e^{-st} d\tau = H(s)e^{st}$$.  
Furthermore, the eigenvalue associated with $$e^{st}$$ is $$H(s)$$.  

### **A Few Standard Fourier Transform Pair**
![Fourierpair]({{ https://github.com/lyons-zhang/lyons-zhang.github.io }}/update/201705/Fourierpair.png){:.aligncenter}
Two useful special cases of any Fourier transform pair are:  
<center>$$u(0)=\int_{-\infty}^{\infty} \hat u(f)df \;\;\;\; \hat u(0)=\int_{-\infty}^{\infty} u(t)dt$$</center>   
Parseval’s theorem:   
<center>$$\int_{-\infty}^{\infty} u(t)v^*(t) dt = \int_{-\infty}^{\infty} \hat u(f) \hat v^*(f) df $$</center>  
Energy equation(replacing $$v(t)$$ by $$u(t)$$):  
<center>$$\int_{-\infty}^{\infty}|u(t)|^2 dt = \int_{-\infty}^{\infty} |\hat u(f)|^2 df$$</center>   
$$|\hat u(f)|^2$$ is called the spectral density of u(t).  
### **Fourier transforms of $$L^1$$ functions**
$$L^1$$ functions always have well-defined Fourier transforms, but the inverse transform does not always have very nice properties.  
Let $$\{ u(t) : \Bbb{R} \to \Bbb{C} \}$$ be $$L^1$$. Then $$\hat u(f) = \int_{-\infty}^{\infty} u(t)e^{−2\pi ift} dt$$ both *exists and satisfies* $$|\hat u(f)| \le \int |u(t)| dt$$ for each $$f \in \Bbb{R}$$. Furthermore, $$\{ \hat u(f) : \Bbb{R} \to \Bbb{C} \}$$ is a *continuous* function of $$f$$.   
Not enough functions are $$L^1$$ to provide suitable models for communication systems. For example, $$sinc(t)$$ is not $$L^1$$.  
Also, functions with discontinuities cannot be Fourier transforms of $$L^1$$ functions.  
Finally, $$L^1$$ functions might have infinite energy. $$L^2$$ functions turn out to be the "right" class.   
### **Fourier transforms of $$L^2$$ functions**
For any $$L^2$$ function $$\{ u(t) : \Bbb{R} \to \Bbb{C} \}$$ and any positive number $$A$$, define $$\hat u_A(f)$$ as the Fourier
transform of the truncation of $$u(t)$$ to $$[-A,A]$$,  
<center>$$\hat u_A(f) = \int_{-A}^A u(t)e^{-2\pi ift} dt$$</center>  
#### **Plancherel part 1**
For any $$L^2$$ function $$\{ u(t) : \Bbb{R} \to \Bbb{C} \}$$, an $$L^2$$ function $$\{ \hat u(f) : \Bbb{R} \to \Bbb{C} \}$$ exists satisfying both  
<center>$$ lim\limits_{A \to \infty} \int_{-\infty}^{\infty} |\hat u(f) - \hat u_A(f)|^2 df = 0$$</center>  
and the energy function.  

For any $$L^2$$ function $$\{ \hat u(f) : \Bbb{R} \to \Bbb{C} \}$$ and any positive number $$B$$, define the inverse transform  
<center>$$u_B(t) = \int_{-B}^B \hat u(f)e^{2\pi ift} df$$</center>  
#### **Plancherel part 2**
For any $$L^2$$ function $$\{ u(t) : \Bbb{R} \to \Bbb{C} \}$$, let $$\{ \hat u(f) : \Bbb{R} \to \Bbb{C} \}$$ be the Fourier transform of Plancherel part 1. Then 
<center>$$ lim\limits_{B \to \infty} \int_{-\infty}^{\infty} |u(t) - u_B(t)|^2 dt = 0$$</center>   
All $$L^2$$ functions have Fourier transforms in the sense of limit in mean-square equivalent ($$L^2$$ equivalent).  
<center>$$\hat u(f) = {l.i.m.}\limits_{A \to \infty} \int_{-A}^A u(t)e^{-2\pi ift} dt; u(t) = {l.i.m.}\limits_{B \to \infty} \int_{-B}^B \hat u(f)e^{-2\pi ift} df$$</center>  
All the Fourier transform relations in the above picture except differentiation hold for all $$L^2$$ functions.   

Reference:  
1. Alan V.Oppenheim. Alan S.Willsky. (1998). *Signals and systems 2nd ed*. (China: Prentice-Hall International,Inc)  
2. MIT Opencourse. *6.02 Introduction to EECS II: Digital Communication Systems*.  
3. MIT Opencourse. *6.003 Signals and Systems*.  
4. MIT Opencourse. *6.450 Principles of Digital Communications I*.  
5. Robert G.Gallager. (2009). *Principles of Digital Communication* (New York: Cambridge University Press).  
6. Harvey Mudd College Opencourse. *E59 Administrative Information*  
7. Terence Tao. (2009). *Analysis I*. *Analysis II* (Hindustan Book Agency)
