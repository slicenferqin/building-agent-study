# 01. 概念专题：双隔离模型：文件系统 + 网络

> 所属主文：[`00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md`](./00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)
>
> 原始来源：[Beyond permission prompts: making Claude Code more secure and autonomous](https://www.anthropic.com/engineering/claude-code-sandboxing)

## 一、概念定义与语义边界
通过两道独立边界同时限制读写与外联，阻断 prompt injection 常见攻击路径。

## 二、原文为何选择该概念（问题-方案匹配）
原文明确指出单边界不足以防止跨域逃逸。

## 三、局限性与失效条件（反例）
1. 策略配置复杂，误配概率高。
2. 某些开发任务确实需要宽权限，策略需动态调整。
3. 过严隔离可能降低开发效率。

## 四、替代路线（至少两条）与 trade-off
- **仅权限弹窗**：初期可行但长期疲劳高。
- **容器沙箱单边界**：有帮助但防护不完整。

## 五、理论推演与创新
可引入“风险分级策略模板”：按任务类型快速切换隔离强度。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Best practices》的 Safe Autonomous Mode 配套时安全收益最大。
- 直接引用目录：
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)
- [Code execution with MCP: Building more efficient agents](../code-execution-with-mcp/00-code-execution-with-mcp-deep-dive.md)
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)

## 七、实战检查清单
- 我是否给“双隔离模型：文件系统 + 网络”定义了可观测指标？
- 我是否为“策略配置复杂，误配概率高。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Beyond permission prompts: making Claude Code more secure and autonomous](https://www.anthropic.com/engineering/claude-code-sandboxing)
- 外部理论锚点：纵深防御；最小权限原则
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
