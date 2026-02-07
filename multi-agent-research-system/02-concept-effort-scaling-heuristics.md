# 02. 概念专题：努力规模化启发式（Effort Scaling）

> 所属主文：[`00-multi-agent-research-system-deep-dive.md`](./00-multi-agent-research-system-deep-dive.md)
>
> 原始来源：[How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)

## 一、概念定义与语义边界
根据问题复杂度分配代理数量与工具调用预算，避免资源错配。

## 二、原文为何选择该概念（问题-方案匹配）
原文指出早期失败常见于“简单题开重炮”或“复杂题投入不足”。

## 三、局限性与失效条件（反例）
1. 复杂度估计本身可能出错。
2. 静态阈值不适应场景漂移。
3. 预算过严会抑制发现关键线索。

## 四、替代路线（至少两条）与 trade-off
- **固定预算**：实现简单但性价比差。
- **完全自适应预算**：潜力大但需要高质量观测信号。

## 五、理论推演与创新
可引入“收益递减探测器”：监测新信息增量，当边际价值下降时自动收敛。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Demystifying evals》中的效率维度评分可直接对接。
- 直接引用目录：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“努力规模化启发式（Effort Scaling）”定义了可观测指标？
- 我是否为“复杂度估计本身可能出错。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)
- 外部理论锚点：资源调度理论；边际收益分析
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
