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

Large language models (LLMs) are demonstrated to excel in many generalization tasks but do not necessarily perform well as standalone reasoning agents in service robots. Recent research has been on integrating LLMs with classical planning methods so LLMs can serve as natural language interfaces to more robust underlying systems. The main limitation that classical planning brings is the requirement for detailed and consistent specifications of the environment. Additionally, service robots are meant to serve as long-term agents, so they must maintain a dynamic memory of the environment that they can (1) update based on multi-modal input and (2) consult with to perform planning tasks; current frameworks do not support this. To address these issues, this paper introduces L3M+P, a framework that uses an external knowledge graph as a memory base to represent an absolute world state. The graph can be updated from multiple sources of information, including natural language interactions with humans. L3M+P will enforce rules for the expected syntax of the absolute world state graph to maintain consistency between graph updates. At planning time, given a natural language description of a task, context will be retrieved from the knowledge graph and provided to the existing LLM+P framework, which will generate a problem specification in the form of a PDDL file that a classical planner can use to solve the task. Our experiments demonstrate that we can achieve 26.5% improvement on correctly registering natural language state changes and 17.5% improvement on generating correct plans by using both knowledge graph retrieval and rule verification on the knowledge graph.