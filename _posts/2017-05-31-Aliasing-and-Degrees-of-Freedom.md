---
title: Aliasing and Degrees of Freedom
description: Aliasing, T-spaced sinc-weighted sinusoid expansion, Degrees of freedom
categories: Digital Communication
---

>  

### **T-spaced sinc-weighted sinusoid expansion**
Let $$u(t) \leftrightarrow \hat u(f)$$ be an arbitrary $$L^2$$ transform pair, and segment $$\hat u(f)$$ into intervals of width $$2W$$.   
<center>$$\hat u(f) = l.i.m.\sum\limits_k \hat v_m(f); \;\;\;\;\; \hat v_m(f) = \hat u(f)rect({f \over 2W} - m)$$</center>
$$\hat v_m(f)$$ is non-zero over $$[2Wm − W, 2Wm + W]$$, so from the sampling theorem for $$[\Delta −W, \Delta +W]$$,   
<center>$$v_m(t) = \sum\limits_k v_m(kT)sinc({t \over T}-k)e^{2\pi i(m/T)(t-kT)} = \sum\limits_k v_m(kT)sinc({t \over T}-k)e^{2\pi imt/T}$$</center>   
Combining all of these *frequency segments*,
<center>$$u(t) = l.i.m.\sum\limits_m v_m(t) = l.i.m.\sum\limits_{m,k} v_m(kT) \psi_{m,k}(t)$$</center>   
The doubly indexed set of orthogonal functions are the time and frequency shifts of the basic function $$\psi_{0,0}(t) = sinc(t/T)$$. The time shifts are in multiples of $$T$$ and the frequency shifts are in multiples of $$1/T$$.   
<center>$$\psi_{m,k}(t) = sinc({t \over T}-k)e^{2\pi imt/T}; \;\;\; m,k \in \Bbb Z$$</center>   
### **T-spaced truncated sinusoid expansion**  
Suppose that an $$L^2$$ waveform $$\{u(t) : R \to C\}$$ is segmented into segments $$u_m(t)$$ of duration $$T$$. Expressing $$u(t)$$ as the sum of these segments   
<center>$$u(t) = l.i.m.\sum\limits_m u_m(t); \;\;\;\;\ u_m(t) = u(t)rect({t \over T} - m)$$</center>
For a function $$\{v(t) : [\Delta −T/2, \Delta +T/2] \to \Bbb C\}$$ centered around some arbitrary time $$\Delta$$, the *shifted Fourier series* over that interval is   
<center>$$v(t) = l.i.m.\sum\limits_k \hat v_k e^{2\pi ikt/T}rect({t-\Delta \over T})$$</center>
<center>$$\hat v_k = {1 \over T}\int_{\Delta-T/2}^{\Delta+T/2}v(t)e^{-2\pi ikt/T}dt, -\infty<k<\infty$$</center>   
Expanding each segment $$u_m(t)$$ by the shifted Fourier series   
<center>$$u_m(t) = l.i.m.\sum\limits_k \hat u_{k,m}e^{2\pi ikt/T}rect({t \over T} - m)$$</center>
<center>$$\hat u_{k,m} = {1 \over T}\int_{mT-T/2}^{mT+T/2}u_m(t)e^{-2\pi ikt/T}dt = {1 \over T}\int_{-\infty}^{\infty}u(t)e^{-2\pi ikt/T}rect({t \over T} - m)dt$$</center>
This expands $$u(t)$$ as a weighted sum of doubly indexed functions   
<center>$$u(t) = l.i.m.\sum\limits_{m,k} \hat u_{k,m} \theta_{m,k}(t), \;\;\;\;\; \text{where}$$</center>
<center>$$\theta_{m,k}(t) = e^{2\pi ikt/T}rect({t \over T} - m)$$</center> 
### **Degrees of freedom**

Reference:  
1. MIT Opencourse. *6.450 Principles of Digital Communications I*.  
2. Robert G.Gallager. (2009). *Principles of Digital Communication* (New York: Cambridge University Press).  
3. J. M. Wozencraft and I. M. Jacobs. (1965) *Principles of Communication Engineering* (John Wiley and Sons, Reprinted by Waveland Press).

