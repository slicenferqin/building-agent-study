# Effective Context Engineering for AI Agents 精读 导读

> 原文：[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
>
> 批次：第一批（方法论地基）

## 本篇定位
从“写好 prompt”升级到“经营整个上下文状态机”。

## 建议阅读顺序
1. [`00-effective-context-engineering-for-ai-agents-deep-dive.md`](./00-effective-context-engineering-for-ai-agents-deep-dive.md)：主精读，聚焦本篇独有命题。
2. [`01-concept-context-as-finite-budget.md`](./01-concept-context-as-finite-budget.md)：上下文作为有限预算（Context as Budget）
3. [`02-concept-just-in-time-context-retrieval.md`](./02-concept-just-in-time-context-retrieval.md)：Just-in-time 上下文检索
4. [`03-concept-long-horizon-memory-architecture.md`](./03-concept-long-horizon-memory-architecture.md)：长时任务记忆架构（压缩+笔记+子代理）

## 跨文直接引用（去重）
以下内容在其他目录已有完整展开，本目录只保留必要连接，不重复铺陈：
- [Introducing Contextual Retrieval](../introducing-contextual-retrieval/00-introducing-contextual-retrieval-deep-dive.md)（概念索引：[`01-concept-contextual-embeddings.md`](../introducing-contextual-retrieval/01-concept-contextual-embeddings.md)）
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)（概念索引：[`01-concept-initializer-coding-dual-loop.md`](../effective-harnesses-for-long-running-agents/01-concept-initializer-coding-dual-loop.md)）
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)（概念索引：[`01-concept-lead-subagent-architecture.md`](../multi-agent-research-system/01-concept-lead-subagent-architecture.md)）

## 目录结构说明
- 主文：`00-effective-context-engineering-for-ai-agents-deep-dive.md`
- 概念专题：3 篇，按“关键概念是否需要独立建模”自适应拆分。
- 引用规范：关键结论引用原文；跨文共通知识直接引用对应目录。
