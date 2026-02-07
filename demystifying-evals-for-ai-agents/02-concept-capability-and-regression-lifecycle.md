# 02. 概念专题：能力评测与回归评测生命周期

> 所属主文：[`00-demystifying-evals-for-ai-agents-deep-dive.md`](./00-demystifying-evals-for-ai-agents-deep-dive.md)
>
> 原始来源：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)

## 一、概念定义与语义边界
能力评测用于爬坡，回归评测用于守城；二者在产品生命周期中会相互转化。

## 二、原文为何选择该概念（问题-方案匹配）
只爬坡不守城会导致“新功能上线、旧能力退化”。

## 三、局限性与失效条件（反例）
1. 转化时机判断困难。
2. 回归集膨胀导致执行成本增加。
3. 老用例可能过时，需定期淘汰。

## 四、替代路线（至少两条）与 trade-off
- **仅能力评测**：创新快但稳定性差。
- **仅回归评测**：稳定强但上限难提升。

## 五、理论推演与创新
可构建“评测分层执行图谱”：提交级、日级、周级分层运行不同套件。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Best practices》中的持续验证实践可无缝对接。
- 直接引用目录：
- [Building effective agents](../building-effective-agents/00-building-effective-agents-deep-dive.md)
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)

## 七、实战检查清单
- 我是否给“能力评测与回归评测生命周期”定义了可观测指标？
- 我是否为“转化时机判断困难。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
- 外部理论锚点：持续交付质量门禁；技术债管理
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
