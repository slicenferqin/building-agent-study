# 02. 概念专题：上下文管理纪律

> 所属主文：[`00-claude-code-best-practices-for-agentic-coding-deep-dive.md`](./00-claude-code-best-practices-for-agentic-coding-deep-dive.md)
>
> 原始来源：[Claude Code: Best practices for agentic coding](https://code.claude.com/docs/en/best-practices)

## 一、概念定义与语义边界
通过清理、压缩和任务分段保持上下文高信号，防止会话退化。

## 二、原文为何选择该概念（问题-方案匹配）
文档明确指出上下文填满会导致遗忘与误判。

## 三、局限性与失效条件（反例）
1. 频繁清理可能丢失隐含背景。
2. 压缩质量依赖提示词与模型状态。
3. 多会话并行时上下文一致性管理更难。

## 四、替代路线（至少两条）与 trade-off
- **单长会话到底**：省切换但质量递减明显。
- **严格短会话**：清爽但跨任务连贯性弱。

## 五、理论推演与创新
可引入“上下文健康仪表板”：显示噪声比例、关键约束存活率与建议清理时机。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Context engineering》中的有限预算观点一体两面。
- 直接引用目录：
- [Equipping agents for the real world with Agent Skills](../equipping-agents-for-the-real-world-with-agent-skills/00-equipping-agents-for-the-real-world-with-agent-skills-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)

## 七、实战检查清单
- 我是否给“上下文管理纪律”定义了可观测指标？
- 我是否为“频繁清理可能丢失隐含背景。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Claude Code: Best practices for agentic coding](https://code.claude.com/docs/en/best-practices)
- 外部理论锚点：认知负荷管理；会话状态机设计
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
