# 03. 概念专题：涌现协作行为与评测方法

> 所属主文：[`00-multi-agent-research-system-deep-dive.md`](./00-multi-agent-research-system-deep-dive.md)
>
> 原始来源：[How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)

## 一、概念定义与语义边界
多代理会出现非预设协作行为，评测应从结果与合理过程双重审视。

## 二、原文为何选择该概念（问题-方案匹配）
原文强调多代理路径多样，强路径约束会误伤有效策略。

## 三、局限性与失效条件（反例）
1. 结果导向评测可能放过高风险路径。
2. 过程导向评测可能过度僵化。
3. 人类审阅成本随代理数上升。

## 四、替代路线（至少两条）与 trade-off
- **纯结果评分**：扩展快但难解释。
- **纯过程评分**：可解释但易抑制创新。

## 五、理论推演与创新
建议采用“结果主导 + 风险过程抽检”的混合评测，平衡创新与安全。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《A postmortem》中的监控与根因分析经验形成闭环。
- 直接引用目录：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“涌现协作行为与评测方法”定义了可观测指标？
- 我是否为“结果导向评测可能放过高风险路径。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)
- 外部理论锚点：复杂系统理论；安全工程中的纵深防御
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
