# 02. 概念专题：pass^k：一致性导向的可靠性指标

> 所属主文：[`00-the-think-tool-deep-dive.md`](./00-the-think-tool-deep-dive.md)
>
> 原始来源：[The "think" tool: Enabling Claude to stop and think](https://www.anthropic.com/engineering/claude-think-tool)

## 一、概念定义与语义边界
pass^k 衡量同一任务重复执行时“全部成功”的概率，更关注稳定性而非偶然命中。

## 二、原文为何选择该概念（问题-方案匹配）
客户服务等场景容错低，单次成功不能代表系统可上线。

## 三、局限性与失效条件（反例）
1. 高 k 下分数下降快，可能打击团队信心。
2. 需要更多试验样本，评测成本上升。
3. 不适合完全创造型任务的唯一指标。

## 四、替代路线（至少两条）与 trade-off
- **pass@k**：适合探索能力评估，但对稳定性刻画弱。
- **单次准确率**：成本低，但易掩盖波动风险。

## 五、理论推演与创新
建议将 pass^k 与业务损失函数绑定，例如错一次就高损失的场景采用更高 k 门槛。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Demystifying evals》中的多层评估方法高度兼容。
- 直接引用目录：
- [Introducing advanced tool use on the Claude Developer Platform](../introducing-advanced-tool-use/00-introducing-advanced-tool-use-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)

## 七、实战检查清单
- 我是否给“pass^k：一致性导向的可靠性指标”定义了可观测指标？
- 我是否为“高 k 下分数下降快，可能打击团队信心。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[The "think" tool: Enabling Claude to stop and think](https://www.anthropic.com/engineering/claude-think-tool)
- 外部理论锚点：可靠性工程；统计显著性检验
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
