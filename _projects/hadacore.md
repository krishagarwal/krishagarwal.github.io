---
title: "HadaCore: Tensor Core Accelerated Hadamard Transform Kernel"
collection: projects
permalink: /projects/hadacore
excerpt: ''
date: 2024-12-12
paperurl: 'https://arxiv.org/abs/2412.08832'
authors: 'Krish Agarwal, Rishi Astra, Adnan Hoque, Mudhakar Srivatsa, Raghu Ganti, Less Wright, Sijia Chen'
---

[arXiv](https://arxiv.org/abs/2412.08832) | 
[Blog](https://pytorch.org/blog/hadacore/) |
[Code](https://github.com/pytorch-labs/applied-ai/tree/main/kernels/cuda/inference/hadamard_transform)

We present HadaCore, a modified Fast Walsh-Hadamard Transform (FWHT) algorithm optimized for the Tensor Cores present in modern GPU hardware. HadaCore follows the recursive structure of the original FWHT algorithm, achieving the same asymptotic runtime complexity but leveraging a hardware-aware work decomposition that benefits from Tensor Core acceleration. This reduces bottlenecks from compute and data exchange. On Nvidia A100 and H100 GPUs, HadaCore achieves speedups of 1 1-1.4x and 1.0-1.3x, with a peak gain of 3.5x and 3.6x respectively, when compared to the existing state-of-the-art implementation of the original algorithm. We also show that when using FP16 or BF16, our implementation is numerically accurate, enabling comparable accuracy on MMLU benchmarks when used in an end-to-end Llama3 inference run with quantized (FP8) attention.