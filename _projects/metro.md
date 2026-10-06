---
title: "Efficient MoE Serving in the Memory-Bound Regime: Balance Activated Experts, Not Tokens"
collection: projects
permalink: /projects/metro
excerpt: 'Preprint, 2025'
date: 2025-12-10
paperurl: 'https://arxiv.org/abs/2512.09277'
authors: 'Yanpeng Yu*, Haiyue Ma*, Krish Agarwal, Nicolai Oswald, Qijing Huang, Hugo Linsenmaier, Chunhui Mei, Ritchie Zhao, Ritika Borkar, Bita Darvish Rouhani, David Nellans, Ronny Krashinsky, Anurag Khandelwal (*equal contribution)'
---

[Paper](https://arxiv.org/abs/2512.09277)

Expert Parallelism (EP) permits Mixture of Experts (MoE) models to scale beyond a single GPU. To address load imbalance across GPUs in EP, existing approaches aim to balance the number of tokens each GPU processes. Surprisingly, we find that this objective degrades performance rather than improving it when processing is memory-bound - a common occurrence in MoE serving, especially in the decode phase. Our analysis reveals that balancing the number of tokens processed per GPU increases the number of activated experts, exacerbating memory pressure in the memory-bound regime. We propose Minimum Expert Token ROuting, a novel token-routing algorithm for high-performance expert-parallel MoE serving in the memory-bound regime that balances the number of activated experts per GPU rather than token counts. METRO achieves near-optimal routing quality with minimal computational overhead by jointly optimizing algorithmic efficiency and leveraging the GPU's parallel processing power. To guarantee routing quality, METRO also employs a novel allGather scheme to gather global top-k knowledge, which has minimal overhead compared to conventional allToAll. Our evaluation of METRO against EPLB on both real systems (vLLM over 8 A100 GPUs) and a proprietary simulator (8-16 B200 GPUs) shows that METRO reduces decode latency by 11 - 22%, and total token throughput by 3 - 21% for Qwen3 and DeepSeek-V3 serving, where prefill and decode phases are co-deployed. In addition, by trading latency headroom for throughput, METRO improves decode throughput by up to 4.11x over EPLB at a fixed decode SLO.
