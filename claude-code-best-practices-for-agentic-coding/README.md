# Claude Code Best Practices 精读 导读

> 原文：[Claude Code: Best practices for agentic coding](https://code.claude.com/docs/en/best-practices)
>
> 批次：第二批（系统化工程、评测、安全与复盘）

## 本篇定位
把“如何高效与安全地用 coding agent”从经验贴整理为可操作方法论。

## 建议阅读顺序
1. [`00-claude-code-best-practices-for-agentic-coding-deep-dive.md`](./00-claude-code-best-practices-for-agentic-coding-deep-dive.md)：主精读，聚焦本篇独有命题。
2. [`01-concept-verify-first-loop.md`](./01-concept-verify-first-loop.md)：Verify-first 协作闭环
3. [`02-concept-context-management-discipline.md`](./02-concept-context-management-discipline.md)：上下文管理纪律
4. [`03-concept-safe-autonomous-mode.md`](./03-concept-safe-autonomous-mode.md)：Safe Autonomous Mode 的边界实践

## 跨文直接引用（去重）
以下内容在其他目录已有完整展开，本目录只保留必要连接，不重复铺陈：
- [Equipping agents for the real world with Agent Skills](../equipping-agents-for-the-real-world-with-agent-skills/00-equipping-agents-for-the-real-world-with-agent-skills-deep-dive.md)（概念索引：[`01-concept-progressive-disclosure.md`](../equipping-agents-for-the-real-world-with-agent-skills/01-concept-progressive-disclosure.md)）
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)（概念索引：[`01-concept-initializer-coding-dual-loop.md`](../effective-harnesses-for-long-running-agents/01-concept-initializer-coding-dual-loop.md)）
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)（概念索引：[`01-concept-dual-isolation.md`](../beyond-permission-prompts-claude-code-sandboxing/01-concept-dual-isolation.md)）

## 目录结构说明
- 主文：`00-claude-code-best-practices-for-agentic-coding-deep-dive.md`
- 概念专题：3 篇，按“关键概念是否需要独立建模”自适应拆分。
- 引用规范：关键结论引用原文；跨文共通知识直接引用对应目录。
