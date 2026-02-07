# 01. 概念专题：Workflow 与 Agent 的边界治理

> 所属主文：[`00-building-effective-agents-deep-dive.md`](./00-building-effective-agents-deep-dive.md)
>
> 原始来源：[Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)

## 一、概念定义与语义边界
该概念讨论“谁来决定下一步行动”：是预定义控制流，还是模型基于上下文与反馈自决。

## 二、原文为何选择该概念（问题-方案匹配）
原文把边界前置，是为了避免团队在“追求智能感”时过度自治，造成调试成本和风险失控。

## 三、局限性与失效条件（反例）
1. 边界判断在中等复杂任务中最难：既不是纯模板，也未达到需要完全自治。
2. 当工具质量差时，自治能力会被错误放大为风险放大器。
3. 组织若缺乏可观测性，边界再清晰也会在上线后失真。

## 四、替代路线（至少两条）与 trade-off
- **固定流程优先**：以确定性为核心，适合强合规任务，但对长尾问题弹性差。
- **自治优先**：探索能力强，但需要成熟评测和沙箱体系才能托底。

## 五、理论推演与创新
可引入“动态边界开关”：同一任务在执行中根据风险信号切换 workflow/agent 模式，例如在高风险动作前强制回到流程态。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：可与《Effective harnesses for long-running agents》的会话切片策略联动，把自治边界延伸到跨窗口执行。
- 直接引用目录：
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“Workflow 与 Agent 的边界治理”定义了可观测指标？
- 我是否为“边界判断在中等复杂任务中最难：既不是纯模板，也未达到需要完全自治。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)
- 外部理论锚点：有限理性（Bounded Rationality）；控制论中的反馈回路
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
