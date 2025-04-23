---
weight: 1
title: "UMASSCTF 2025 - OddOneOut"
date: 2025-04-19
lastmod: 2025-04-19
draft: false
author: "0xB4tm4n"
authorLink: "https://darkn3ssy.github.io/"
description: "Writeup for the Misc challenge in UMASSCTF 2025."

tags: ["Investigation", "MISC", "Stegano", "python", "RGB"]
categories: ["Writeups"]

lightgallery: true

math:
  enable: true

toc:
  enable: true
---
OddOneOut [misc]

- **Description**
    
    > I forgot to organize my encrypted flags for this challenge! Can you find the odd one out? I could have sworn it was a different color...
- View Hint
    
    Not all solvers will work on this. If you get stuck, try a different way! 
    
- View Hint
    
    The oddoneout challenge is multilayer! You'll know you have the right one if it looks like a real word
    

![OddOneOut.png](https://github.com/user-attachments/assets/27d8bf7f-8cde-4d84-a5c4-b16f531458cd)

So, what I did is, first thing I ran `zsteg`

I got this:

![image](https://github.com/user-attachments/assets/94114f0b-e6e4-4282-a151-eede3c112d54)


I Noticed  a useless String 

I read the description carefully, and it mentioned something about it being a different color. The hint also talked about multiple layers, so I ran `zsteg-mask`, which extracted the layers with different colors. Then, I got this image

![image](https://github.com/user-attachments/assets/88e98583-3e52-4f5f-9ee5-050e91d9f367)


I scanned that QR code it gives me this  **`UMASS{{rcckuizufzxhznod}}`**  I thought it's the flag but when I tried to submit it … incorrect . hmm while I was thinking I noticed this black image that I got too from `zsteg-mask` 

![image](https://github.com/user-attachments/assets/cee17f67-6670-4c78-a128-2756327efd2e)

there was some data at the top I tried to extract those using `https://stegonline.georgeom.net/upload`

I got this 

`when i tried to extract i got this what i got now Man I RE  ALLY lik  e square  s. I thi  nk cubes   are coo  l too. Q  R codes   are trul  y the pi  nnacle o  f modern   data en  coding..  .Also, w  hile you  're root  ing arou  nd in he  re, I'm   taking a   poll: d  id you e  ver play   coolmat  h games   as a kid  ?..If yo  u did: g  reat! I   hope you   played   Bloxorz.  .If you   didn't:   that's a   travest  y and yo  u should   go play   Bloxorz   right n  ow. Or m  aybe aft  er you s  olve thi  s challe  nge. It'  s the ke  y to all   your pr  oblems.. this is all i got s`

at the end it says `Bloxorz` its the key to all your problems

then I went to cyber chef to try some ciphers … it was Vigenere cipher

`Bloxorz + {rcckuizufzxhznod} = {qrongratulations}` 

![image](https://github.com/user-attachments/assets/b89cdce7-3f7e-499b-8ad1-cc1b4aea3a71)

 

so the final flag is `UMASS{qrongratulations}`
