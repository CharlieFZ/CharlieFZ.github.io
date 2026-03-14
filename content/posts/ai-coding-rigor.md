---
title: "科研中的AI编程：从过度依赖到负责任使用"
date: 2026-03-14
draft: false
description: "Nature Computational Science 的一篇文章让我重新审视自己使用AI编程工具的方式"
tags: ["AI4Science", "科研方法", "反思"]
categories: ["科研笔记"]
---


今天读到 Nature Computational Science 上的一篇文章：[Threats to scientific software from over-reliance on AI code assistants](https://www.nature.com/articles/s43588-025-00845-2)。文章指出，科研软件对AI编码助手的过度依赖正在构成威胁——因为大多数研究代码缺乏测试，而科学家的编程训练往往不足。

这让我想到自己最近的状态：AI一次性生成几百行代码，我直接运行、看结果、写论文。**代码跑通了，但我真的理解每一步在做什么吗？**

这不只是我一个人的困境。
- Anthropic 的研究显示，被动依赖AI仅一小时，开发者的概念理解和调试能力就下降17%
- Stack Overflow 2025调查：96%的开发者不完全信任AI生成的代码，但不到一半会认真审查
- AI生成的代码产生的逻辑错误比人类代码多1.75倍（Qodo 2025报告）

在网页编写当中，vibe coding值得信赖，以至于有人说“前端已死”，我这网站99%依赖于claude code构建，甚至这篇博文AI成分也不小于50%。
但在科研场景中，科研代码中的**静默错误**（silent bugs）会给出一个"看起来合理"的结果，然后这个错误的结果就进了论文，错误结论被引用，直到50年以后被考古学家发现。更哲学地说，vibe coding侵犯人类于自然科学的主体性

我决定改变自己的工作方式，我列出了一下四点原则：
1.言必及引用
2.代码分段给出
3.审核后方可加入脚本
4.决策记录于日志

具体细节如下：
“”（请codex帮我填充这一块内容，用人话）
## 一句话总结

NLP研究者 Joris Baan 用了几个月 AI 编程工具后的结论说得好：

> "You need to be able to write and understand everything yourself to use it responsibly."

AI是工具，不是替代品。能用好AI的前提是你自己得先明白。

---

*相关文献：*
- O'Brien, G. (2025). Threats to scientific software from over-reliance on AI code assistants. *Nature Computational Science*.
- Poldrack, R. Ten simple rules for AI-assisted coding to maintain scientific rigor. *The Transmitter*.
- Baan, J. (2025). Can coding agents help write scientific code responsibly?
