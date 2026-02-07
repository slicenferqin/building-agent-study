# 03. 概念专题：Safe Autonomous Mode 的边界实践

> 所属主文：[`00-claude-code-best-practices-for-agentic-coding-deep-dive.md`](./00-claude-code-best-practices-for-agentic-coding-deep-dive.md)
>
> 原始来源：[Claude Code: Best practices for agentic coding](https://code.claude.com/docs/en/best-practices)

## 一、概念定义与语义边界
自治模式应与沙箱隔离共同使用，在可控边界内释放自动化。

## 二、原文为何选择该概念（问题-方案匹配）
文档对 `--dangerously-skip-permissions` 给出明确风险提示。

## 三、局限性与失效条件（反例）
1. 边界配置错误会导致假安全。
2. 安全模式可能限制部分复杂操作。
3. 用户容易高估自治模式可靠性。

## 四、替代路线（至少两条）与 trade-off
- **全权限自治**：效率高但风险高。
- **全人工审批**：安全感强但效率低。

## 五、理论推演与创新
可采用“任务级自治档位”：根据任务风险自动选择权限策略组合。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Sandboxing》文章在理念与实施上直接互补。
- 直接引用目录：
- [Equipping agents for the real world with Agent Skills](../equipping-agents-for-the-real-world-with-agent-skills/00-equipping-agents-for-the-real-world-with-agent-skills-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)

## 七、实战检查清单
- 我是否给“Safe Autonomous Mode 的边界实践”定义了可观测指标？
- 我是否为“边界配置错误会导致假安全。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Claude Code: Best practices for agentic coding](https://code.claude.com/docs/en/best-practices)
- 外部理论锚点：风险分级控制；纵深防御模型
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
