# 03. 概念专题：增量推进与 Clean State 纪律

> 所属主文：[`00-effective-harnesses-for-long-running-agents-deep-dive.md`](./00-effective-harnesses-for-long-running-agents-deep-dive.md)
>
> 原始来源：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)

## 一、概念定义与语义边界
每轮只做小步可验变更，并保证会话结束时仓库处于可继续开发的健康状态。

## 二、原文为何选择该概念（问题-方案匹配）
原文明确指出“做太多、收不住”是长任务最常见失败模式。

## 三、局限性与失效条件（反例）
1. 过小增量可能拖慢总进度。
2. clean state 标准若模糊，会被形式化绕过。
3. 复杂依赖改动下保持 clean state 成本高。

## 四、替代路线（至少两条）与 trade-off
- **大步迭代**：速度快但回滚风险大。
- **严格微步迭代**：稳定高但管理成本增加。

## 五、理论推演与创新
可采用“风险加权增量”：高风险模块小步、低风险模块中步，动态调整粒度。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Best practices》的 verify-first 与 checkpoint 思路一致。
- 直接引用目录：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)

## 七、实战检查清单
- 我是否给“增量推进与 Clean State 纪律”定义了可观测指标？
- 我是否为“过小增量可能拖慢总进度。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- 外部理论锚点：持续集成实践；最小可行变更（MVC）
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
