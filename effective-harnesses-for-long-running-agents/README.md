# Effective Harnesses for Long-running Agents 精读 导读

> 原文：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
>
> 批次：第二批（系统化工程、评测、安全与复盘）

## 本篇定位
解决跨多上下文窗口长期任务的连续性与可交接问题。

## 建议阅读顺序
1. [`00-effective-harnesses-for-long-running-agents-deep-dive.md`](./00-effective-harnesses-for-long-running-agents-deep-dive.md)：主精读，聚焦本篇独有命题。
2. [`01-concept-initializer-coding-dual-loop.md`](./01-concept-initializer-coding-dual-loop.md)：Initializer/Coding 双循环架构
3. [`02-concept-artifact-continuity.md`](./02-concept-artifact-continuity.md)：工件连续性（Artifact Continuity）
4. [`03-concept-incremental-clean-state.md`](./03-concept-incremental-clean-state.md)：增量推进与 Clean State 纪律

## 跨文直接引用（去重）
以下内容在其他目录已有完整展开，本目录只保留必要连接，不重复铺陈：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-context-as-finite-budget.md`](../effective-context-engineering-for-ai-agents/01-concept-context-as-finite-budget.md)）
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)（概念索引：[`01-concept-verify-first-loop.md`](../claude-code-best-practices-for-agentic-coding/01-concept-verify-first-loop.md)）
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)（概念索引：[`01-concept-overlapping-incident-diagnosis.md`](../a-postmortem-of-three-recent-issues/01-concept-overlapping-incident-diagnosis.md)）

## 目录结构说明
- 主文：`00-effective-harnesses-for-long-running-agents-deep-dive.md`
- 概念专题：3 篇，按“关键概念是否需要独立建模”自适应拆分。
- 引用规范：关键结论引用原文；跨文共通知识直接引用对应目录。
