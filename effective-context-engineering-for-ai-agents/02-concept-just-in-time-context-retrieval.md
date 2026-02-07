# 02. 概念专题：Just-in-time 上下文检索

> 所属主文：[`00-effective-context-engineering-for-ai-agents-deep-dive.md`](./00-effective-context-engineering-for-ai-agents-deep-dive.md)
>
> 原始来源：[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)

## 一、概念定义与语义边界
只保留可索引引用，运行时按需拉取上下文，减少预加载污染。

## 二、原文为何选择该概念（问题-方案匹配）
原文指出许多团队从预检索转向运行时探索，以获得更高任务适应性。

## 三、局限性与失效条件（反例）
1. 运行时探索增加延迟。
2. 工具语义不清会导致“盲搜”与死路。
3. 在强实时场景中，JIT 可能不满足 SLA。

## 四、替代路线（至少两条）与 trade-off
- **全量预检索**：响应快，但易引入无关上下文。
- **混合检索**：兼顾速度与准确，但系统复杂度更高。

## 五、理论推演与创新
可采用“分层检索触发器”：先轻量元数据筛选，再重数据拉取，最后按需反思补检。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Advanced tool use》的 Tool Search Tool 在理念上同构：都是按需显式加载。
- 直接引用目录：
- [Introducing Contextual Retrieval](../introducing-contextual-retrieval/00-introducing-contextual-retrieval-deep-dive.md)
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)

## 七、实战检查清单
- 我是否给“Just-in-time 上下文检索”定义了可观测指标？
- 我是否为“运行时探索增加延迟。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- 外部理论锚点：分层缓存策略；探索式信息检索
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
