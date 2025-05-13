---
title: "L3M+P: Lifelong Planning with Large Language Models"
collection: projects
permalink: /projects/l3mp
excerpt: ''
date: 2025-03-06
paperurl: 'http://krishagarwal.github.io/files/l3mp.pdf'
authors: 'Krish Agarwal, Yuqian Jiang, Jiaheng Hu, Bo Liu, Peter Stone'
---

[Paper](http://krishagarwal.github.io/files/l3mp.pdf) |
[Code](https://github.com/krishagarwal/l3m-p)

By combining classical planning methods with large language models (LLMs), recent research such as LLM+P has enabled agents to plan for general tasks given in natural language. However, scaling these methods to general-purpose service robots remains challenging: (1) classical planning algorithms generally require a detailed and consistent specification of the environment, which is not always readily available; and (2) existing frameworks mainly focus on isolated planning tasks, whereas robots are often meant to serve in long-term continuous deployments, and therefore must maintain a dynamic memory of the environment which can be updated with multi-modal inputs and extracted as planning knowledge for future tasks. To address these two issues, this paper introduces L3M+P (Lifelong LLM+P), a framework that uses an external knowledge graph as a representation of the world state. The graph can be updated from multiple sources of information, including sensory input and natural language interactions with humans. L3M+P enforces rules for the expected format of the absolute world state graph to maintain consistency between graph updates. At planning time, given a natural language description of a task, L3M+P retrieves context from the knowledge graph and generates a problem definition for classical planners. Evaluated on household robot simulators and on a real-world service robot, L3M+P achieves significant improvement over baseline methods both on accurately registering natural language state changes and on correctly generating plans, thanks to the knowledge graph retrieval and verification.