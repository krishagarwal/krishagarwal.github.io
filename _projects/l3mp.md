---
title: "L3M+P: Lifelong Optimal Planning with Large Language Models"
collection: projects
permalink: /projects/l3mp
excerpt: ''
date: 2024-12-01
paperurl: 'http://krishagarwal.github.io/files/l3mp.pdf'
authors: 'Krish Agarwal, Yuqian Jiang, Jiaheng Hu, Bo Liu, Peter Stone'
---

[Paper](http://krishagarwal.github.io/files/l3mp.pdf) |
[Code](https://github.com/krishagarwal/LLLMP)

Enabling the creation of general-purpose service robots is a long-standing research ambition for the field of autonomous robotics. This ambition has only grown with the widespread adoption of large language models (LLMs), which are demonstrated to excel in many generalization tasks but do not necessarily perform well as standalone reasoning agents. Recent research has focused on integrating LLMs with classical planning methods so LLMs can serve as natural language interfaces to more robust underlying systems. There are two issues that prevent this approach from scaling to general-purpose service robots. First, classical planning algorithms generally require a detailed and consistent specification of the environment, which is not always readily available. Second, service robots are often meant to serve in long-term continuous deployments, so they must maintain a dynamic memory of the environment that can be updated with multi-modal inputs and extracted as planning knowledge for any task; existing frameworks mainly focus on isolated planning tasks. To address these two issues at once, this paper introduces L3M+P, a framework that uses an external knowledge graph as a memory base to represent an absolute world state. The graph can be updated from multiple sources of information, including natural language interactions with humans. L3M+P enforces rules for the expected format of the absolute world state graph to maintain consistency between graph updates. At planning time, given a natural language description of a task, context is retrieved from the knowledge graph and provided to the existing LLM+P framework, which generates a problem specification in the form of a PDDL file that a classical planner can use to solve the task. Our experiments demonstrate that L3M+P achieves 26.5\% improvement on correctly registering natural language state changes and 17.5\% improvement on generating correct plans by using both knowledge graph retrieval and rule verification on the knowledge graph, when compared to a straightforward extension of LLM+P.