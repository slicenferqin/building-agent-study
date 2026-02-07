# Introducing Advanced Tool Use 精读 导读

> 原文：[Introducing advanced tool use on the Claude Developer Platform](https://www.anthropic.com/engineering/advanced-tool-use)
>
> 批次：第一批（方法论地基）

## 本篇定位
在大规模工具库条件下，解决“找得到、调得对、跑得动”三连问题。

## 建议阅读顺序
1. [`00-introducing-advanced-tool-use-deep-dive.md`](./00-introducing-advanced-tool-use-deep-dive.md)：主精读，聚焦本篇独有命题。
2. [`01-concept-tool-search-tool.md`](./01-concept-tool-search-tool.md)：Tool Search Tool：工具按需发现机制
3. [`02-concept-programmatic-tool-calling.md`](./02-concept-programmatic-tool-calling.md)：Programmatic Tool Calling：代码化工具编排
4. [`03-concept-tool-use-examples.md`](./03-concept-tool-use-examples.md)：Tool Use Examples：示例化调用协议

## 跨文直接引用（去重）
以下内容在其他目录已有完整展开，本目录只保留必要连接，不重复铺陈：
- [Code execution with MCP: Building more efficient agents](../code-execution-with-mcp/00-code-execution-with-mcp-deep-dive.md)（概念索引：[`01-concept-code-first-tool-orchestration.md`](../code-execution-with-mcp/01-concept-code-first-tool-orchestration.md)）
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)（概念索引：[`01-concept-tool-ergonomics.md`](../writing-effective-tools-for-agents/01-concept-tool-ergonomics.md)）
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-context-as-finite-budget.md`](../effective-context-engineering-for-ai-agents/01-concept-context-as-finite-budget.md)）

## 目录结构说明
- 主文：`00-introducing-advanced-tool-use-deep-dive.md`
- 概念专题：3 篇，按“关键概念是否需要独立建模”自适应拆分。
- 引用规范：关键结论引用原文；跨文共通知识直接引用对应目录。
