# 你好，我是 Jay 👋

[English](./README.md)

我是一名 CS 学生，目前主要探索 **AI Agent Runtime、Agent Evaluation 与自适应执行策略**。

我更喜欢通过构建小而可观察的系统来学习，并围绕具体问题做实验：Agent 应该如何导航大型代码仓库？什么时候复杂执行策略真的值得额外成本？Runtime 又应该依据什么信号做策略选择？

> **构建 → 测量 → 检查失败 → 迭代。**

## 主要项目

### [mini-Pi](https://github.com/justlearner010/mini-Pi)

**一个刻意保持小而可读的 TypeScript 终端 Agent，用来研究 Coding Agent 的内部机制。**

mini-Pi 的目标不是复刻一个功能齐全的 Coding Assistant，而是尽量保持 Runtime 紧凑，让我可以直接研究其中每一层：LLM Provider、Tool Calling、Agent Loop、上下文管理、代码仓库导航、工具权限、CLI/TUI 与评测。

目前主要包含：

- 面向 TypeScript / JavaScript 项目的有界、语法级 **Repo Index**；
- 根据问题生成紧凑候选上下文的 **Query-aware Repo Map**；
- 由 Runtime 强制执行的工具权限边界；
- 面向代码仓库导航行为的本地确定性实验与真实 Provider 评测。

一次外部仓库评测暴露出简单词面排序的问题：产品代码 Top-3 只有 **1/5**；加入 scope、package 与角色信息后，在同一五道任务上提升到 **5/5**。这个项目真正关注的并不是单个数字，而是完整闭环：先实现机制，再测量，找到失败点，然后修改设计继续验证。

→ [项目仓库](https://github.com/justlearner010/mini-Pi) · [实验记录](https://github.com/justlearner010/mini-Pi/tree/main/docs/experiments)

---

### [Adaptive Agent Runtime Lab](https://github.com/justlearner010/adaptive-agent-runtime-lab)

**一个研究型实验仓库，核心问题是：面对不同任务，Agent 应该选择哪一种执行策略？**

Runtime 在统一评测框架下实现并比较 **Direct、ReAct 与 Subagent**，通过结构化 trace 记录正确率、LLM 调用次数、token、延迟、工具调用与子代理数量等指标。

当前实验闭环是：

`Task → Policy → Execution Strategy → Trace → Evaluation`

目前单模型、小规模 benchmark 的阶段性结果显示：简单执行策略的基线比直觉更强——Direct 在 **31/40** 个已评测任务上是成本意义下的最优策略，而需要外部语料搜索的任务则明显需要 ReAct。这里我把它们视为特定实验条件下的阶段性发现，而不是普遍结论。

长期我想继续研究：是否可以让 Runtime 根据任务特征与运行时信号学习策略选择，而不是依赖固定规则。

→ [项目仓库](https://github.com/justlearner010/adaptive-agent-runtime-lab) · [研究笔记](https://github.com/justlearner010/adaptive-agent-runtime-lab/blob/main/RESEARCH.md)

## 我正在研究的问题

- 在上下文预算有限时，Coding Agent 应该如何导航大型代码仓库？
- ReAct、Planning、Subagent 在什么情况下值得额外的 token 与延迟？
- Agent Runtime 应该依据哪些信号选择执行策略？
- 除了最终答案正确率，我们应该如何评价 Agent 的运行过程？
- 哪些可靠性与安全边界应该由 Runtime 代码强制保证，而不是交给模型自己决定？

## 我的工作方式

我更看重能够留下证据的项目：

- 做**可以真正运行的系统**，而不只是画架构图；
- 用**benchmark 与 trace**验证判断，而不只依赖直觉；
- 同时记录**失败案例、限制与负结果**；
- 尽量形成可重复的 **Issue → 实现 → 评测 → 修正** 工程循环。

我还处在学习和积累阶段，因此更愿意把这些仓库当作实验室：每个项目都应该让我真正理解一点 Agent System 的行为，而不是只给简历再增加一个框架名词。

## 其他项目

- [Adaptive Learning Agent](https://github.com/justlearner010/adaptive-learning-agent) — 一个 notebook-first 的学习 Agent，把学习画像、阶段计划、理论检查与代码 Lab 连接起来。
- [CLI Text Tool](https://github.com/justlearner010/jay-first-cli-text-tool) — 一个经过测试的 Python 文本处理 CLI，支持统计、分块、结构化 JSON 输出与模拟摘要。

## 联系我

- GitHub: [@justlearner010](https://github.com/justlearner010)

如果你也在研究 **Agent Runtime、Agent Evaluation、Coding Agent 或执行策略**，欢迎交流 benchmark、实验结果和失败案例。
