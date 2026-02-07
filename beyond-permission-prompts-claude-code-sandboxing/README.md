# Beyond Permission Prompts 精读 导读

> 原文：[Beyond permission prompts: making Claude Code more secure and autonomous](https://www.anthropic.com/engineering/claude-code-sandboxing)
>
> 批次：第二批（系统化工程、评测、安全与复盘）

## 本篇定位
在提升自治效率的同时，系统性降低提示注入与误操作风险。

## 建议阅读顺序
1. [`00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md`](./00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)：主精读，聚焦本篇独有命题。
2. [`01-concept-dual-isolation.md`](./01-concept-dual-isolation.md)：双隔离模型：文件系统 + 网络
3. [`02-concept-bounded-autonomy.md`](./02-concept-bounded-autonomy.md)：有界自治（Bounded Autonomy）
4. [`03-concept-policy-proxy-governance.md`](./03-concept-policy-proxy-governance.md)：策略代理（Policy Proxy）治理

## 跨文直接引用（去重）
以下内容在其他目录已有完整展开，本目录只保留必要连接，不重复铺陈：
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)（概念索引：[`01-concept-verify-first-loop.md`](../claude-code-best-practices-for-agentic-coding/01-concept-verify-first-loop.md)）
- [Code execution with MCP: Building more efficient agents](../code-execution-with-mcp/00-code-execution-with-mcp-deep-dive.md)（概念索引：[`01-concept-code-first-tool-orchestration.md`](../code-execution-with-mcp/01-concept-code-first-tool-orchestration.md)）
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)（概念索引：[`01-concept-overlapping-incident-diagnosis.md`](../a-postmortem-of-three-recent-issues/01-concept-overlapping-incident-diagnosis.md)）

## 目录结构说明
- 主文：`00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md`
- 概念专题：3 篇，按“关键概念是否需要独立建模”自适应拆分。
- 引用规范：关键结论引用原文；跨文共通知识直接引用对应目录。
