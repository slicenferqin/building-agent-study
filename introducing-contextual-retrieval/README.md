# Introducing Contextual Retrieval 精读 导读

> 原文：[Introducing Contextual Retrieval](https://www.anthropic.com/engineering/contextual-retrieval)
>
> 批次：第一批（方法论地基）

## 本篇定位
解决传统 RAG“分块后语义断裂”导致召回失败的问题。

## 建议阅读顺序
1. [`00-introducing-contextual-retrieval-deep-dive.md`](./00-introducing-contextual-retrieval-deep-dive.md)：主精读，聚焦本篇独有命题。
2. [`01-concept-contextual-embeddings.md`](./01-concept-contextual-embeddings.md)：Contextual Embeddings：分块前缀语义增强
3. [`02-concept-contextual-bm25.md`](./02-concept-contextual-bm25.md)：Contextual BM25：稀疏检索的再语境化
4. [`03-concept-reranking-tradeoff.md`](./03-concept-reranking-tradeoff.md)：Reranking 的收益-延迟权衡

## 跨文直接引用（去重）
以下内容在其他目录已有完整展开，本目录只保留必要连接，不重复铺陈：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-context-as-finite-budget.md`](../effective-context-engineering-for-ai-agents/01-concept-context-as-finite-budget.md)）
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)（概念索引：[`01-concept-lead-subagent-architecture.md`](../multi-agent-research-system/01-concept-lead-subagent-architecture.md)）
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-grader-taxonomy.md`](../demystifying-evals-for-ai-agents/01-concept-grader-taxonomy.md)）

## 目录结构说明
- 主文：`00-introducing-contextual-retrieval-deep-dive.md`
- 概念专题：3 篇，按“关键概念是否需要独立建模”自适应拆分。
- 引用规范：关键结论引用原文；跨文共通知识直接引用对应目录。
