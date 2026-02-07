# 01. 概念专题：Initializer/Coding 双循环架构

> 所属主文：[`00-effective-harnesses-for-long-running-agents-deep-dive.md`](./00-effective-harnesses-for-long-running-agents-deep-dive.md)
>
> 原始来源：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)

## 一、概念定义与语义边界
首次会话负责建制，后续会话负责增量交付，形成“搭台+演进”的职责分离。

## 二、原文为何选择该概念（问题-方案匹配）
原文观察到一体化提示难兼顾初始化完整性与迭代效率。

## 三、局限性与失效条件（反例）
1. 初始化质量差会把后续全部拖偏。
2. 职责分离增加提示与流程管理成本。
3. 切换规则不清会产生重复劳动。

## 四、替代路线（至少两条）与 trade-off
- **单会话全能模式**：简单但跨窗口稳定性差。
- **多专职代理模式**：专业化高但协调更复杂。

## 五、理论推演与创新
可引入“初始化验收门”：初始化未达标不允许进入编码循环。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Multi-agent research system》的角色分工思想相通。
- 直接引用目录：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)

## 七、实战检查清单
- 我是否给“Initializer/Coding 双循环架构”定义了可观测指标？
- 我是否为“初始化质量差会把后续全部拖偏。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- 外部理论锚点：软件工程中的启动阶段治理；阶段门（Stage-gate）模型
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
