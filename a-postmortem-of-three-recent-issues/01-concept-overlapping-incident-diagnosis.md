# 01. 概念专题：重叠故障诊断（Overlapping Incident Diagnosis）

> 所属主文：[`00-a-postmortem-of-three-recent-issues-deep-dive.md`](./00-a-postmortem-of-three-recent-issues-deep-dive.md)
>
> 原始来源：[A postmortem of three recent issues](https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues)

## 一、概念定义与语义边界
多个独立缺陷在时间和流量路径上叠加，会制造看似随机且矛盾的症状。

## 二、原文为何选择该概念（问题-方案匹配）
原文时间线显示三类问题交织，显著增加排障难度。

## 三、局限性与失效条件（反例）
1. 传统单因果排障思维不适用。
2. 日志维度不够时难以区分故障叠加。
3. 跨平台差异会掩盖共因。

## 四、替代路线（至少两条）与 trade-off
- **串行排障**：步骤清晰但慢。
- **并行假设验证**：速度快但组织成本高。

## 五、理论推演与创新
建议建立“故障假设图谱”：并行管理候选根因并动态更新置信度。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Demystifying evals》的 transcript 深读方法互补。
- 直接引用目录：
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“重叠故障诊断（Overlapping Incident Diagnosis）”定义了可观测指标？
- 我是否为“传统单因果排障思维不适用。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[A postmortem of three recent issues](https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues)
- 外部理论锚点：事故指挥系统（ICS）；贝叶斯根因推断
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
