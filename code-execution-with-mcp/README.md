# Code Execution with MCP 精读 导读

> 原文：[Code execution with MCP: Building more efficient agents](https://www.anthropic.com/engineering/code-execution-with-mcp)
>
> 批次：第二批（系统化工程、评测、安全与复盘）

## 本篇定位
从“模型逐次工具调用”迁移到“模型写代码编排工具”，提升效率与控制力。

## 建议阅读顺序
1. [`00-code-execution-with-mcp-deep-dive.md`](./00-code-execution-with-mcp-deep-dive.md)：主精读，聚焦本篇独有命题。
2. [`01-concept-code-first-tool-orchestration.md`](./01-concept-code-first-tool-orchestration.md)：代码优先工具编排
3. [`02-concept-privacy-preserving-data-flow.md`](./02-concept-privacy-preserving-data-flow.md)：隐私保留的数据流控制
4. [`03-concept-stateful-execution-and-resume.md`](./03-concept-stateful-execution-and-resume.md)：状态化执行与可恢复工作流

## 跨文直接引用（去重）
以下内容在其他目录已有完整展开，本目录只保留必要连接，不重复铺陈：
- [Introducing advanced tool use on the Claude Developer Platform](../introducing-advanced-tool-use/00-introducing-advanced-tool-use-deep-dive.md)（概念索引：[`01-concept-tool-search-tool.md`](../introducing-advanced-tool-use/01-concept-tool-search-tool.md)）
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)（概念索引：[`01-concept-dual-isolation.md`](../beyond-permission-prompts-claude-code-sandboxing/01-concept-dual-isolation.md)）
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)（概念索引：[`01-concept-tool-ergonomics.md`](../writing-effective-tools-for-agents/01-concept-tool-ergonomics.md)）

## 目录结构说明
- 主文：`00-code-execution-with-mcp-deep-dive.md`
- 概念专题：3 篇，按“关键概念是否需要独立建模”自适应拆分。
- 引用规范：关键结论引用原文；跨文共通知识直接引用对应目录。
