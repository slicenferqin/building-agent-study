# 02. 概念专题：隐私保留的数据流控制

> 所属主文：[`00-code-execution-with-mcp-deep-dive.md`](./00-code-execution-with-mcp-deep-dive.md)
>
> 原始来源：[Code execution with MCP: Building more efficient agents](https://www.anthropic.com/engineering/code-execution-with-mcp)

## 一、概念定义与语义边界
通过执行环境内处理和令牌化映射，让敏感数据完成业务流转但不进入模型上下文。

## 二、原文为何选择该概念（问题-方案匹配）
原文给出 PII tokenization 机制，展示了“可用与安全并存”的实现路径。

## 三、局限性与失效条件（反例）
1. 映射表泄露会造成次级风险。
2. 复杂数据联结可能绕过脱敏策略。
3. 策略配置错误会导致假安全。

## 四、替代路线（至少两条）与 trade-off
- **全量上送模型**：实现快但合规风险高。
- **完全离线人工处理**：安全高但自动化低。

## 五、理论推演与创新
建议引入“数据流策略单测”：对允许/禁止路径做自动化验证。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Claude Code sandboxing》的网络与文件边界一起形成纵深防御。
- 直接引用目录：
- [Introducing advanced tool use on the Claude Developer Platform](../introducing-advanced-tool-use/00-introducing-advanced-tool-use-deep-dive.md)
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“隐私保留的数据流控制”定义了可观测指标？
- 我是否为“映射表泄露会造成次级风险。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Code execution with MCP: Building more efficient agents](https://www.anthropic.com/engineering/code-execution-with-mcp)
- 外部理论锚点：数据最小化原则；隐私计算中的脱敏映射
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
