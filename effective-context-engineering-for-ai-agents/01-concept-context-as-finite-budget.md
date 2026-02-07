# 01. 概念专题：上下文作为有限预算（Context as Budget）

> 所属主文：[`00-effective-context-engineering-for-ai-agents-deep-dive.md`](./00-effective-context-engineering-for-ai-agents-deep-dive.md)
>
> 原始来源：[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)

## 一、概念定义与语义边界
把上下文看作预算约束下的资源分配问题，而不是无限存储空间。

## 二、原文为何选择该概念（问题-方案匹配）
原文用 context rot 说明“多即好”会失效，必须做信号筛选。

## 三、局限性与失效条件（反例）
1. 预算估算常受任务波动影响，难以一次定标。
2. 过度节流会损伤探索能力。
3. 团队若缺乏观测工具，预算策略难以落地。

## 四、替代路线（至少两条）与 trade-off
- **粗放上下文堆叠**：开发快，但回忆与推理质量随窗口膨胀下降。
- **精细预算治理**：质量稳，但需要持续维护和指标体系。

## 五、理论推演与创新
建议引入“token 账本”：按会话阶段记录 token 去向（指令、工具、历史、结果）并做回溯优化。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Demystifying evals》结合可构建“质量-成本”联合评分。
- 直接引用目录：
- [Introducing Contextual Retrieval](../introducing-contextual-retrieval/00-introducing-contextual-retrieval-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)

## 七、实战检查清单
- 我是否给“上下文作为有限预算（Context as Budget）”定义了可观测指标？
- 我是否为“预算估算常受任务波动影响，难以一次定标。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- 外部理论锚点：信息论中的信噪比；约束优化思想
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
