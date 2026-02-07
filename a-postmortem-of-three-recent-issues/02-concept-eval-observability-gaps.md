# 02. 概念专题：评测盲区与可观测性缺口

> 所属主文：[`00-a-postmortem-of-three-recent-issues-deep-dive.md`](./00-a-postmortem-of-three-recent-issues-deep-dive.md)
>
> 原始来源：[A postmortem of three recent issues](https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues)

## 一、概念定义与语义边界
评测若缺乏灵敏度和线上映射能力，会让真实退化长期潜伏。

## 二、原文为何选择该概念（问题-方案匹配）
原文明确承认评测未能捕捉用户报告中的退化模式。

## 三、局限性与失效条件（反例）
1. 高灵敏度评测可能增加误报。
2. 隐私限制削弱数据可见性。
3. 线上分布变化快，离线集易过时。

## 四、替代路线（至少两条）与 trade-off
- **离线评测主导**：成本可控但真实贴合度有限。
- **线上监控主导**：真实强但反应滞后。

## 五、理论推演与创新
可引入“反馈指纹聚类”：把零散用户反馈自动聚类映射到潜在技术变更。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Demystifying evals》的多层防线框架高度一致。
- 直接引用目录：
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“评测盲区与可观测性缺口”定义了可观测指标？
- 我是否为“高灵敏度评测可能增加误报。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[A postmortem of three recent issues](https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues)
- 外部理论锚点：可观测性三支柱；弱信号检测
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
