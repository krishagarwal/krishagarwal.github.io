---
title: "Tensor Core Accelerated Kernels for Hadamard and Fourier Masked Attention"
collection: projects
permalink: /projects/hadamard_fourier_masked_attn
excerpt: ''
date: 2025-05-06
paperurl: 'https://apps.cs.utexas.edu/apps/tech-reports/206107'
authors: 'Krish Agarwal'
---

[Thesis](https://apps.cs.utexas.edu/apps/tech-reports/206107) |
[Code](https://github.com/krishagarwal/hadamard-fourier-masked-attn)

Softmax attention incurs quadratic time complexity in sequence length, making it the primary bottleneck in transformer training and inference for long sequences. Structured Masked Attention (SMA) offers a sub-quadratic alternative by removing softmax normalization and applying a structured matrix as the attention mask. Dropping softmax enables reformulating elementwise masking as a matrix multiplication, allowing the use of fast transform algorithms to compute the operation in sub-quadratic time when the mask is structured.

Implementing SMA for a given structured mask is straightforward if a standalone fast transform implementation is available. However, standard implementations of these transforms often achieve low hardware utilization on GPUs because they do not leverage high-throughput matrix-multiply units like Tensor Cores. Furthermore, using a separate kernel to perform the transform prevents operator fusion, missing critical opportunities to reuse data in on-chip SRAM.

In this work, we address these challenges for SMA when using Walsh-Hadamard and discrete Fourier transform matrices, both of which admit O(n log n) algorithms for computing matrix-vector products. Specifically, we design fused, Tensor Core accelerated kernels to efficiently perform inference and backpropagation for Hadamard and Fourier masked attention while retaining sub-quadratic time complexity.