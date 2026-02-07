# How We Built Our Multi-agent Research System 精读 导读

> 原文：[How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)
>
> 批次：第二批（系统化工程、评测、安全与复盘）

## 本篇定位
解释多代理系统为何在高价值研究任务上显著优于单代理，以及代价何在。

## 建议阅读顺序
1. [`00-multi-agent-research-system-deep-dive.md`](./00-multi-agent-research-system-deep-dive.md)：主精读，聚焦本篇独有命题。
2. [`01-concept-lead-subagent-architecture.md`](./01-concept-lead-subagent-architecture.md)：Lead/Subagent/Citation 三层结构
3. [`02-concept-effort-scaling-heuristics.md`](./02-concept-effort-scaling-heuristics.md)：努力规模化启发式（Effort Scaling）
4. [`03-concept-emergent-coordination-evals.md`](./03-concept-emergent-coordination-evals.md)：涌现协作行为与评测方法

## 跨文直接引用（去重）
以下内容在其他目录已有完整展开，本目录只保留必要连接，不重复铺陈：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-context-as-finite-budget.md`](../effective-context-engineering-for-ai-agents/01-concept-context-as-finite-budget.md)）
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-grader-taxonomy.md`](../demystifying-evals-for-ai-agents/01-concept-grader-taxonomy.md)）
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)（概念索引：[`01-concept-initializer-coding-dual-loop.md`](../effective-harnesses-for-long-running-agents/01-concept-initializer-coding-dual-loop.md)）

## 目录结构说明
- 主文：`00-multi-agent-research-system-deep-dive.md`
- 概念专题：3 篇，按“关键概念是否需要独立建模”自适应拆分。
- 引用规范：关键结论引用原文；跨文共通知识直接引用对应目录。
