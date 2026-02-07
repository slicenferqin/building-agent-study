# 02. 概念专题：工件连续性（Artifact Continuity）

> 所属主文：[`00-effective-harnesses-for-long-running-agents-deep-dive.md`](./00-effective-harnesses-for-long-running-agents-deep-dive.md)
>
> 原始来源：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)

## 一、概念定义与语义边界
用结构化工件承载跨会话记忆，降低摘要误差和口语化交接风险。

## 二、原文为何选择该概念（问题-方案匹配）
长任务中“知道做过什么”比“记得聊过什么”更重要。

## 三、局限性与失效条件（反例）
1. 工件维护额外占用开发时间。
2. 工件格式不统一会削弱可读性。
3. 工件与代码状态不同步会误导后续会话。

## 四、替代路线（至少两条）与 trade-off
- **纯对话摘要**：成本低但可追溯性弱。
- **纯 git 历史**：可信高但语义上下文不足。

## 五、理论推演与创新
建议建立“工件一致性检查器”：自动校验 feature 状态、提交记录和测试结果是否对齐。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Context engineering》的结构化 note-taking 形成统一方法。
- 直接引用目录：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)

## 七、实战检查清单
- 我是否给“工件连续性（Artifact Continuity）”定义了可观测指标？
- 我是否为“工件维护额外占用开发时间。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- 外部理论锚点：可追溯性工程；知识管理中的显性化策略
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
