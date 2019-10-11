---
layout: post
title:  "Interspeech 2019 Voice Conversion Paper Review"
date:   2019-10-10 02:11:09
author: softrime 
---
> For Interspeech 2019, this year there are two sessions about Voice Conversion(VC). In this post, I would mostly review VC-related papers in session **'
Neural Techniques for Voice Conversion and Waveform Generation'**, which is mainly about speaker information transformation. It is interesting that **StarGAN** becomes very popular this year. All the three papers about StarGAN tries to improve performace by modifying its architecture or training strategy. Also is **One-shot Learning VC** (three papers) which convert source speech to arbitrary target speaker with very limited target speaker corpus. One of them uses VAE while other two methods use PPG. There are also three VC works named on Tomoki Toda which all based on VAE framework. (W.I.P)

<!--more-->

{: class="table-of-content"}
* TOC
{:toc}

----

### Summary 

| | Title | Task | Framework  |Author | Affiliation |
| ---- | ---- | ---- | ---- | ---- | ---- |
| 1 | Non-Parallel Voice Conversion Using Weighted Generative Adversarial Networks | Non-parallel; many-to-many | StarGAN; WORLD | Dipjyoti Paul | University of Crete, Greece |
| 2 | One-Shot Voice Conversion by Separating Speaker and Content Representations with Instance Normalization | Non-parallel; One-shot |  |  Ju-chieh Chou; (Hung-yi Lee) | National Taiwan University |
| 3 | One-Shot Voice Conversion with Global Speaker Embeddings | Non-parallel; One-shot |  | Hui Lu; (Helen Meng) | Tsinghua-CUHK |
| 4 | Non-Parallel Voice Conversion with Cyclic Variational Autoencoder | Non-parallel; one-to-one |  | Patrick Lumban Tobing; (Tomoki Toda) | Nagoya University |
| 5 | StarGAN-VC2: Rethinking Conditional Methods for StarGAN-Based Voice Conversion | Non-parallel; many-to-many |  | Takuhiro Kaneko | NTT |
| 6 | Fast Learning for Non-Parallel Many-to-Many Voice Conversion with Residual Star Generative Adversarial Networks | Non-parallel; many-to-many |  |Shengkui Zhao | Alibaba Group(Damo) |
| 7 | One-Shot Voice Conversion with Disentangled Representations by Leveraging Phonetic Posteriorgrams | Non-parallel; One-shot |  | Seyed Hamidreza Mohammadi | ObEN |
| 8 | Investigation of F0 Conditioning and Fully Convolutional Networks in Variational Autoencoder Based Voice Conversion | Non-parallel; one-to-one |  | Wen-Chin Huang; (Tomoki Toda) | Nagoya University |
| 9 | Robustness of Statistical Voice Conversion Based on Direct Waveform Modification Against Background Sounds | Environment Robustness |  | Yusuke Kurita; (Tomoki Toda) | Nagoya University |
| 10 | Jointly Trained Conversion Model and WaveNet Vocoder for Non-Parallel Voice Conversion Using Mel-Spectrograms and Phonetic Posteriorgrams | Non-parallel; inf-to-one |  | Songxiang Liu; (Lifa Sun); (Helen Meng) | CUHK |
| 11 | Group Latent Embedding for Vector Quantized Variational Autoencoder in Non-Parallel Voice Conversion | Non-parallel; one-to-one |  | Shaojin Ding | Texas A&M University |
| 12 | Semi-Supervised Voice Conversion with Amortized Variational Inference | Semi-optimized; one-to-one |  | Cory Stephenson | Intel AI Lab |


### Review
#### Non-Parallel Voice Conversion Using Weighted Generative Adversarial Networks 

This paper modifies loss function in StarGAN. In detail, authors add a weight factor on the adversarial loss when update Generators, which means $$ w_iD(G(x_i, c)) $$ . The weight can be considered as the fake confidence for a sample. It reduces the loss of samples which is considered as fake with a high confidence by Discriminator. 


