# 02. 概念专题：评测驱动工具迭代

> 所属主文：[`00-writing-effective-tools-for-agents-deep-dive.md`](./00-writing-effective-tools-for-agents-deep-dive.md)
>
> 原始来源：[Writing effective tools for agents — with agents](https://www.anthropic.com/engineering/writing-tools-for-agents)

## 一、概念定义与语义边界
通过代表性任务集、可验证标准和长期回归体系持续改进工具，而非一次性定型。

## 二、原文为何选择该概念（问题-方案匹配）
工具问题往往体现在复杂多步任务里，只有 eval 才能把“偶发错”转化为可复现信号。

## 三、局限性与失效条件（反例）
1. 评测集覆盖不全时，会出现“评测通过、线上翻车”。
2. 评分器不稳会放大噪音，导致错误优化方向。
3. 高频评测有成本压力，需要分层运行策略。

## 四、替代路线（至少两条）与 trade-off
- **人工抽样评审**：深度高但速度慢，不适合高频迭代。
- **线上投诉驱动**：贴近真实但严重滞后，回归难控制。

## 五、理论推演与创新
建议构建“失败样例市场”：把典型失败自动转为新任务并打标签（参数错误/路径错误/语义错误）。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Demystifying evals for AI agents》互补：本篇讲工具 eval，后者讲系统级 eval。
- 直接引用目录：
- [Building effective agents](../building-effective-agents/00-building-effective-agents-deep-dive.md)
- [Introducing advanced tool use on the Claude Developer Platform](../introducing-advanced-tool-use/00-introducing-advanced-tool-use-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“评测驱动工具迭代”定义了可观测指标？
- 我是否为“评测集覆盖不全时，会出现“评测通过、线上翻车”。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Writing effective tools for agents — with agents](https://www.anthropic.com/engineering/writing-tools-for-agents)
- 外部理论锚点：测试驱动开发（TDD）；质量成本模型（CoQ）
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
