# 01. 概念专题：渐进披露（Progressive Disclosure）技能架构

> 所属主文：[`00-equipping-agents-for-the-real-world-with-agent-skills-deep-dive.md`](./00-equipping-agents-for-the-real-world-with-agent-skills-deep-dive.md)
>
> 原始来源：[Equipping agents for the real world with Agent Skills](https://claude.com/blog/equipping-agents-for-the-real-world-with-agent-skills)

## 一、概念定义与语义边界
通过多层信息加载策略让 agent 只在需要时读取更深细节，控制上下文成本。

## 二、原文为何选择该概念（问题-方案匹配）
原文强调这是 Skill 可扩展的核心，不然技能越多越拖慢系统。

## 三、局限性与失效条件（反例）
1. 触发策略错误会导致关键技能未加载。
2. 层级过深会增加搜索开销。
3. 作者若不维护目录语义，渐进披露会失效。

## 四、替代路线（至少两条）与 trade-off
- **全量技能预载**：简单但上下文开销大。
- **完全手动调用**：可控但自动化程度低。

## 五、理论推演与创新
可加入“技能热度缓存”：近期高频技能优先驻留，冷技能按需回收。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Context engineering》的高信号上下文原则直接呼应。
- 直接引用目录：
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)

## 七、实战检查清单
- 我是否给“渐进披露（Progressive Disclosure）技能架构”定义了可观测指标？
- 我是否为“触发策略错误会导致关键技能未加载。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Equipping agents for the real world with Agent Skills](https://claude.com/blog/equipping-agents-for-the-real-world-with-agent-skills)
- 外部理论锚点：分层存储思想；注意力预算模型
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
