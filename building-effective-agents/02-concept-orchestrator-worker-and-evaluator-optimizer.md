# 02. 概念专题：Orchestrator-Worker 与 Evaluator-Optimizer 组合范式

> 所属主文：[`00-building-effective-agents-deep-dive.md`](./00-building-effective-agents-deep-dive.md)
>
> 原始来源：[Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)

## 一、概念定义与语义边界
前者负责分解与并行，后者负责质量收敛；二者组合形成“先发散、后收敛”的系统行为。

## 二、原文为何选择该概念（问题-方案匹配）
单一循环难以兼顾探索广度与结果质量，组合范式可以把搜索和判别解耦。

## 三、局限性与失效条件（反例）
1. 协调消息过多会挤压上下文预算。
2. 评估器若标准模糊，会把优化循环拉成无效内耗。
3. 并行 worker 的结果可能出现语义冲突，需要额外融合策略。

## 四、替代路线（至少两条）与 trade-off
- **纯并行投票**：实现简单、速度快，但深度推理与纠错能力有限。
- **单代理深推理**：上下文一致性高，但在大任务上效率与覆盖不足。

## 五、理论推演与创新
可以将 evaluator 变为“预算感知裁判”：在质量提升边际下降时提前终止优化，避免无穷循环。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Demystifying evals for AI agents》里的分层评测体系天然互补：结构循环 + 结构评估。
- 直接引用目录：
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“Orchestrator-Worker 与 Evaluator-Optimizer 组合范式”定义了可观测指标？
- 我是否为“协调消息过多会挤压上下文预算。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)
- 外部理论锚点：OODA 决策环；多臂老虎机中的探索-利用权衡
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
