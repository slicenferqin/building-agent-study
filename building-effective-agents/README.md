# Building Effective Agents 精读 导读

> 原文：[Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)
>
> 批次：第一批（方法论地基）

## 本篇定位
回答一个根本问题：什么情况下应该用 agent，什么情况下根本不该上 agent。

## 建议阅读顺序
1. [`00-building-effective-agents-deep-dive.md`](./00-building-effective-agents-deep-dive.md)：主精读，聚焦本篇独有命题。
2. [`01-concept-workflow-vs-agent-boundary.md`](./01-concept-workflow-vs-agent-boundary.md)：Workflow 与 Agent 的边界治理
3. [`02-concept-orchestrator-worker-and-evaluator-optimizer.md`](./02-concept-orchestrator-worker-and-evaluator-optimizer.md)：Orchestrator-Worker 与 Evaluator-Optimizer 组合范式
4. [`03-concept-agent-computer-interface.md`](./03-concept-agent-computer-interface.md)：ACI（Agent-Computer Interface）作为一等公民

## 跨文直接引用（去重）
以下内容在其他目录已有完整展开，本目录只保留必要连接，不重复铺陈：
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)（概念索引：[`01-concept-tool-ergonomics.md`](../writing-effective-tools-for-agents/01-concept-tool-ergonomics.md)）
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-grader-taxonomy.md`](../demystifying-evals-for-ai-agents/01-concept-grader-taxonomy.md)）
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-context-as-finite-budget.md`](../effective-context-engineering-for-ai-agents/01-concept-context-as-finite-budget.md)）

## 目录结构说明
- 主文：`00-building-effective-agents-deep-dive.md`
- 概念专题：3 篇，按“关键概念是否需要独立建模”自适应拆分。
- 引用规范：关键结论引用原文；跨文共通知识直接引用对应目录。
