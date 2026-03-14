---
title: "Vibe Coding in Research: How Do We Review Intelligence Greater Than Ourselves?"
date: 2026-03-14
draft: false
description: "Nature Computational Science 的一篇文章让我重新审视自己使用AI编程工具的方式"
tags: ["AI4Science", "科研方法", "反思"]
categories: ["科研笔记"]
cover:
  image: "/images/post-ai-coding.jpg"
  alt: "AI与科研编程"
  relative: false
---

## 起因（引子，真实情况并非如此）

今天读到 Nature Computational Science 上的一篇文章。文章指出，科研软件对 AI 编码助手的过度依赖正在构成威胁——因为大多数研究代码缺乏测试，而科学家的编程训练往往不足 [1]。

这让我想到自己最近的状态：AI 一次性生成几百行代码，我直接运行、看结果、写论文。**代码跑通了，但我真的理解每一步在做什么吗？**

## 这不只是我一个人的困境

- Anthropic 的一项随机对照实验显示，被动依赖 AI 仅一小时，开发者的概念理解和调试能力就**下降 17%**，而速度提升未达到统计显著 [2]。
- Stack Overflow 2025 调查：96% 的开发者不完全信任 AI 生成的代码，但不到一半会认真审查 [3]。
- AI 生成的代码产生的逻辑错误比人类代码**多 1.75 倍** [4]。

## 两种场景，两种态度

在网页编写当中，vibe coding 值得信赖，以至于有人说"前端已死"。我这个网站 99% 依赖 Claude Code 构建，甚至这篇博文的 AI 成分也不小于 50%。

但在科研场景中，情况完全不同。科研代码中的错误可能会给出一个"看起来合理"的结果，然后这个错误的结果就进了论文，错误结论被引用，直到 50 年以后被考古学家发现。

更哲学地说，**vibe coding 正在侵犯人类于自然科学的主体性。**

## 我的四条原则

我决定改变自己的工作方式，尝试性地列出以下四条原则，让codex设置到它的全局文件和skills当中：

### 原则一：言必及引用

只要是可核查的事实、参数、版本、论文结论、网页说法，AI都必须把出处贴在旁边，为了让我自己以后还能回到原点：这句话是谁说的，这个默认值从哪来的，这个判断到底是证据，还是我当时的猜测。

Nature Computational Science 那篇评论提醒得很直接：科研软件尤其容易出事，因为很多研究代码本来就缺测试，而不少科学家又缺系统的软件开发训练 [1]。是的，我有幸而不幸地在2024年进入大学，作为“AI native generation”，基础的代码学习变得比以往二十年任何时候都更困难而不是更简单——前人踏出的大道外有了一条容易踏上的滑坡。既然如此，更不能把"AI 说得像真的"当成"真的"。

### 原则二：代码分段给出

AI 最容易让我放松警惕的，不是它报错，而是它一次生成几百行看起来很顺的代码，让我直接跳到"先跑一下再说"。

Anthropic 在 2026 年 1 月 29 日发布的实验中，让 52 名软件工程师边做任务边学一个不熟悉的 Python 库；使用 AI 的那组，在任务后立刻进行的测验里平均低了 17%，而速度提升没有达到统计显著 [2]。这至少说明一件事：如果我的目标不只是"把代码写出来"，还包括"把方法学会、把错误看懂"，那我就不能把整个实现过程外包给一个聊天框。

### 原则三：审核后方可加入脚本

以后 AI 给我的代码，默认都只是草案，不是成品。没有逐段看过，没有问清输入输出，就不允许把它写进主脚本。

NLP 研究者 Joris Baan 在一篇博文里写得很直白：

> "I think you need to be able to write and understand everything yourself to be able to use it responsibly." [5]

对我来说，这句话的人话版就是：**AI 可以替我省体力，但不能替我承担理解责任。**

### 原则四：决策记录于日志

科研里最可怕的不是明显报错，而是那种"结果看起来挺合理"的静默错误。所以以后每次重要改动，我都会尽量留下几行记录：为什么换这个实现，为什么接受 AI 的建议，为什么改参数，为什么删掉某个异常值，为什么相信这次重构不会改变结论。

这样等我两周后回头看，或者合作者来问，至少还能还原当时的判断路径。

## 结语

我不是要拒绝 AI，也没有能力拒绝它。当流水线将钟表的价格民主化，古法编程将会和手工表一样成为昂贵的奢侈品。但是要把它放回合适的位置：它可以是提案机、脚手架、陪练、加速器。但不能替代人对于科学性的解释权

这点其实也和开发者群体的现实很一致。Stack Overflow 2025 调查显示，84% 的受访者已经在用或计划使用 AI 工具，但对其输出"信任"的只有 33%，而"不信任"的有 46% [3]。问题从来不是"用不用 AI"，而是**"用了以后谁来核、怎么核"**。

具体实现方案请见我的github仓库：https://github.com/CharlieFZ/WHITEBOX-AGENTS.md-skills
---

## 参考文献

[1] O'Brien, G. (2025). Threats to scientific software from over-reliance on AI code assistants. *Nature Computational Science*. https://www.nature.com/articles/s43588-025-00845-2

[2] Anthropic Research. (2026). How AI assistance impacts the formation of coding skills. https://www.anthropic.com/research/AI-assistance-coding-skills

[3] Stack Overflow. (2025). 2025 Developer Survey — AI Section. https://survey.stackoverflow.co/2025/ai

[4] Qodo. (2025). State of AI code quality in 2025. https://www.qodo.ai/reports/state-of-ai-code-quality/

[5] Baan, J. (2025). Can coding agents help write scientific code responsibly? https://jorisbaan.nl/2025/10/17/can-coding-agents-help-write-scientific-code-responsibly.html
