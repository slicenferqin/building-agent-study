# 01. 概念专题：Think Tool 与 Extended Thinking 的功能边界

> 所属主文：[`00-the-think-tool-deep-dive.md`](./00-the-think-tool-deep-dive.md)
>
> 原始来源：[The "think" tool: Enabling Claude to stop and think](https://www.anthropic.com/engineering/claude-think-tool)

## 一、概念定义与语义边界
两者都提供额外思考空间，但触发时机和任务适配不同：前者偏中途反思，后者偏前置规划。

## 二、原文为何选择该概念（问题-方案匹配）
原文更新指出多数场景可优先 extended thinking，但复杂工具链仍有 think 的价值。

## 三、局限性与失效条件（反例）
1. 边界不清会导致重复思考与浪费 token。
2. 前置思考过重会拖慢响应。
3. 中途反思过频会打断执行节奏。

## 四、替代路线（至少两条）与 trade-off
- **纯前置规划**：结构清晰，但难覆盖运行时新信息。
- **纯过程反思**：适应强，但可能缺少全局计划。

## 五、理论推演与创新
可采用“前置-中途双层思考预算器”：先规划，再按不确定度触发 think。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Advanced tool use》的程序化调用结合可减少“边走边猜”的风险。
- 直接引用目录：
- [Introducing advanced tool use on the Claude Developer Platform](../introducing-advanced-tool-use/00-introducing-advanced-tool-use-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)

## 七、实战检查清单
- 我是否给“Think Tool 与 Extended Thinking 的功能边界”定义了可观测指标？
- 我是否为“边界不清会导致重复思考与浪费 token。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[The "think" tool: Enabling Claude to stop and think](https://www.anthropic.com/engineering/claude-think-tool)
- 外部理论锚点：元认知理论；双系统决策模型
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
