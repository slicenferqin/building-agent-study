# 03. 概念专题：状态化执行与可恢复工作流

> 所属主文：[`00-code-execution-with-mcp-deep-dive.md`](./00-code-execution-with-mcp-deep-dive.md)
>
> 原始来源：[Code execution with MCP: Building more efficient agents](https://www.anthropic.com/engineering/code-execution-with-mcp)

## 一、概念定义与语义边界
利用文件系统保存中间结果，使代理可跨步骤/跨会话恢复任务。

## 二、原文为何选择该概念（问题-方案匹配）
长链任务中，状态持久化是提升鲁棒性的关键，而非附属能力。

## 三、局限性与失效条件（反例）
1. 状态文件治理不善会造成一致性问题。
2. 恢复逻辑复杂时容易引发重复执行。
3. 状态兼容问题会影响升级。

## 四、替代路线（至少两条）与 trade-off
- **无状态即席执行**：简单但中断后恢复差。
- **外部工作流引擎托管状态**：稳健但接入复杂。

## 五、理论推演与创新
可实现“状态快照 + 差分回放”机制，提升可调试与可回滚能力。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Long-running harnesses》的进度工件理念互相验证。
- 直接引用目录：
- [Introducing advanced tool use on the Claude Developer Platform](../introducing-advanced-tool-use/00-introducing-advanced-tool-use-deep-dive.md)
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“状态化执行与可恢复工作流”定义了可观测指标？
- 我是否为“状态文件治理不善会造成一致性问题。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Code execution with MCP: Building more efficient agents](https://www.anthropic.com/engineering/code-execution-with-mcp)
- 外部理论锚点：事件溯源（Event Sourcing）；检查点恢复机制
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
