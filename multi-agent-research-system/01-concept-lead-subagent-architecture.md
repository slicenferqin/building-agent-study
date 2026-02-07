# 01. 概念专题：Lead/Subagent/Citation 三层结构

> 所属主文：[`00-multi-agent-research-system-deep-dive.md`](./00-multi-agent-research-system-deep-dive.md)
>
> 原始来源：[How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)

## 一、概念定义与语义边界
把任务分解、并行探索、证据归因拆成三个角色，降低单代理过载。

## 二、原文为何选择该概念（问题-方案匹配）
研究任务天然发散，单代理难兼顾广度、深度与可引用性。

## 三、局限性与失效条件（反例）
1. 角色过多会引入通信与协调开销。
2. 引用代理若标准不稳会影响可信度。
3. 主代理策略错误会系统性放大。

## 四、替代路线（至少两条）与 trade-off
- **单代理深搜**：上下文一致但覆盖有限。
- **无主并行群体**：扩展快但全局一致性弱。

## 五、理论推演与创新
建议加入“证据冲突仲裁器”，在子代理结论矛盾时自动发起复核子任务。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Contextual retrieval》的高质量检索机制可耦合为研究底座。
- 直接引用目录：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“Lead/Subagent/Citation 三层结构”定义了可观测指标？
- 我是否为“角色过多会引入通信与协调开销。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)
- 外部理论锚点：组织设计中的分工协作；黑板系统（Blackboard Architecture）
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
