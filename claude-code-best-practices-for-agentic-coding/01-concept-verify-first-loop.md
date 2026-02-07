# 01. 概念专题：Verify-first 协作闭环

> 所属主文：[`00-claude-code-best-practices-for-agentic-coding-deep-dive.md`](./00-claude-code-best-practices-for-agentic-coding-deep-dive.md)
>
> 原始来源：[Claude Code: Best practices for agentic coding](https://code.claude.com/docs/en/best-practices)

## 一、概念定义与语义边界
先定义可验证标准，再让 agent 执行，是提升一次成功率的核心策略。

## 二、原文为何选择该概念（问题-方案匹配）
原文把验证能力称为最高杠杆，说明反馈环比提示词润色更关键。

## 三、局限性与失效条件（反例）
1. 验证标准本身可能不完整。
2. 某些开放任务难以完全形式化验证。
3. 维护验证脚本需要额外投入。

## 四、替代路线（至少两条）与 trade-off
- **结果感受式验收**：快但不稳定。
- **全自动硬验证**：稳定但灵活性受限。

## 五、理论推演与创新
建议建立“验证模板库”：按任务类型快速生成验收脚手架。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Demystifying evals》形成从个人协作到系统评测的连续谱。
- 直接引用目录：
- [Equipping agents for the real world with Agent Skills](../equipping-agents-for-the-real-world-with-agent-skills/00-equipping-agents-for-the-real-world-with-agent-skills-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)

## 七、实战检查清单
- 我是否给“Verify-first 协作闭环”定义了可观测指标？
- 我是否为“验证标准本身可能不完整。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Claude Code: Best practices for agentic coding](https://code.claude.com/docs/en/best-practices)
- 外部理论锚点：测试驱动思想；反馈控制理论
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
