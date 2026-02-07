# 03. 概念专题：瑞士奶酪式多层评估防线

> 所属主文：[`00-demystifying-evals-for-ai-agents-deep-dive.md`](./00-demystifying-evals-for-ai-agents-deep-dive.md)
>
> 原始来源：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)

## 一、概念定义与语义边界
把离线评测、线上监控、A/B、用户反馈、人工审阅叠加，降低单点漏检。

## 二、原文为何选择该概念（问题-方案匹配）
原文明确指出任何单层方法都有盲区，叠加才可靠。

## 三、局限性与失效条件（反例）
1. 多层系统运维成本高。
2. 跨层指标口径不统一会引发误判。
3. 组织协同不足时难以持续执行。

## 四、替代路线（至少两条）与 trade-off
- **单层离线评测**：便于自动化但对真实世界感知弱。
- **纯线上监控**：真实但代价是用户先受损。

## 五、理论推演与创新
建议引入“跨层异常关联引擎”：自动把线上告警映射到离线用例缺口。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《A postmortem》中的改进项形成直接实施路径。
- 直接引用目录：
- [Building effective agents](../building-effective-agents/00-building-effective-agents-deep-dive.md)
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)

## 七、实战检查清单
- 我是否给“瑞士奶酪式多层评估防线”定义了可观测指标？
- 我是否为“多层系统运维成本高。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
- 外部理论锚点：安全工程瑞士奶酪模型；可靠性工程 SRE 实践
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
