# 03. 概念专题：长时任务记忆架构（压缩+笔记+子代理）

> 所属主文：[`00-effective-context-engineering-for-ai-agents-deep-dive.md`](./00-effective-context-engineering-for-ai-agents-deep-dive.md)
>
> 原始来源：[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)

## 一、概念定义与语义边界
通过三种互补机制跨越上下文窗口限制，维持任务连续性。

## 二、原文为何选择该概念（问题-方案匹配）
单靠窗口变大无法解决污染问题，必须引入结构化状态外置机制。

## 三、局限性与失效条件（反例）
1. 压缩摘要容易丢失隐含约束。
2. 笔记格式不规范会变成噪声仓库。
3. 子代理并行会引入协调与一致性挑战。

## 四、替代路线（至少两条）与 trade-off
- **只做 compaction**：低成本，但复杂任务长期一致性不足。
- **只做多代理**：并行强，但控制与治理压力大。

## 五、理论推演与创新
建议实现“记忆健康度巡检”：定期检查笔记过期率、摘要召回率和子代理冲突率。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Effective harnesses for long-running agents》形成实践闭环。
- 直接引用目录：
- [Introducing Contextual Retrieval](../introducing-contextual-retrieval/00-introducing-contextual-retrieval-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)

## 七、实战检查清单
- 我是否给“长时任务记忆架构（压缩+笔记+子代理）”定义了可观测指标？
- 我是否为“压缩摘要容易丢失隐含约束。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- 外部理论锚点：工作记忆模型；分布式系统中的日志压缩
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
