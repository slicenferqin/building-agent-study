# 01. 概念专题：评分器三分法：代码 / 模型 / 人类

> 所属主文：[`00-demystifying-evals-for-ai-agents-deep-dive.md`](./00-demystifying-evals-for-ai-agents-deep-dive.md)
>
> 原始来源：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)

## 一、概念定义与语义边界
三类评分器各有强弱，必须按任务属性协同使用。

## 二、原文为何选择该概念（问题-方案匹配）
agent 输出既有结构化可验证结果，也有开放文本与行为路径。

## 三、局限性与失效条件（反例）
1. 代码评分器易脆弱。
2. 模型评分器有非确定性。
3. 人工评分扩展性不足。

## 四、替代路线（至少两条）与 trade-off
- **单一代码评分**：便宜但覆盖窄。
- **单一模型评分**：覆盖广但需校准。

## 五、理论推演与创新
建议使用“分维度评分器路由”：不同指标交由最合适评分器负责。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Multi-agent research system》中的 LLM judge 实践相印证。
- 直接引用目录：
- [Building effective agents](../building-effective-agents/00-building-effective-agents-deep-dive.md)
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)

## 七、实战检查清单
- 我是否给“评分器三分法：代码 / 模型 / 人类”定义了可观测指标？
- 我是否为“代码评分器易脆弱。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
- 外部理论锚点：测量理论；评估者一致性（Inter-rater reliability）
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
