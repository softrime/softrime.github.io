---
layout: post
title:  "Interspeech 2019 Voice Conversion Paper Review"
date:   2019-10-10 02:11:09
author: softrime 
---
> For Interspeech 2019, this year there are two sessions about Voice Conversion(VC). For my personal interests, I would mostly review VC-related papers in session **'
Neural Techniques for Voice Conversion and Waveform Generation'**. (Still work in progress)

<!--more-->

{: class="table-of-content"}
* TOC
{:toc}

#### Non-Parallel Voice Conversion Using Weighted Generative Adversarial Networks 

This paper modifies loss function in StarGAN. In detail, authors add a weight factor on the adversarial loss when update Generators, which means $w_iD(G(x_i, c))$ . The weight can be considered as the fake confidence for a sample. It reduces the loss of samples which is considered as fake with a high confidence by Discriminator. 
