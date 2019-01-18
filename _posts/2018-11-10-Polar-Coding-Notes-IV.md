---
title:   Polar Coding Notes IV
description: 
categories: Digital Comunication
---

>  Consider a $$G_N$$-coset code with parameter $$(N, K, \cal A, u_{{\cal A}^c})$$. Let $$u_1^N$$ be encoded into a codeword $$x_1^N$$, let $$x_1^N$$ be sent over the channel $$W^N$, and let a channel output $$y_1^N$$ be received. The decoder’s task is to generate an estimate $$\hat u_1^N$$ of $$u_1^N$$, given knowledge of $$\cal A$$, $$u_{{\cal A}^c}$$, and $$y_1^N^[1]$$. 
  
#### **Successive Cancellation Decoder**    
Individual $$G_N$$-coset codes will be identified by a parameter vector $$(N, K, \cal A, u_{{\cal A}^c})$$, where $$K$$ is the code dimension and specifies the size of $$\cal A$$. The ratio $$K/N$$ is called the code rate. We will refer to $$\cal A$$ as the information set and to $$u_{{\cal A}^c} \in {\cal X}^{N−K}$$ as frozen bits or vector.  
We obtain a mapping from source blocks $$u_{\cal A}$$ to codeword blocks $$x_1^N$$ as  
<center>$$x_1^N = u_1^N G_N = u_{\cal A}G_N(\cal A) \oplus u_{{\cal A}^c}G_N({\cal A}^c)$$</center>  


Reference:  
1. E. Arikan. *Channel polarization: A method for constructing capacity-achieving codes for symmetric binary-input memoryless channels*. IEEE Trans. on Information Theory, vol.55, no.7, pp.3051–3073, July 2009.  
2. A. D. Wyner and J. Ziv. *A theorem on the entropy of certain binary sequences and applications (Part I)*. IEEE Trans.Inform.Theory, vol.19, no.6, pp.769-772, Nov.1973.  
3. Abbas El Gamal and Young-Han Kim. *Network Information Theory*. Cambridge University Press. 2011.  
4. M.Alsan and E.Telatar. *A simple proof of polarization and polarization for non-stationary memoryless channels*. IEEE Trans.Info.Theory, vol.62, no.9,pp.4873-4878. 2016.  
5. Vincent Y. F. Tan. *EE5139R: Information Theory for Communication Systems:2016/7, Semester 1*. https://www.ece.nus.edu.sg/  
6. Eren Sasoglu. *Polarization and Polar Codes*. Foundations and Trends in Communications and Information Theory Vol. 8, No. 4 (2011) 259–381  


