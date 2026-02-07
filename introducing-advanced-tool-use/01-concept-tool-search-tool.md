# 01. 概念专题：Tool Search Tool：工具按需发现机制

> 所属主文：[`00-introducing-advanced-tool-use-deep-dive.md`](./00-introducing-advanced-tool-use-deep-dive.md)
>
> 原始来源：[Introducing advanced tool use on the Claude Developer Platform](https://www.anthropic.com/engineering/advanced-tool-use)

## 一、概念定义与语义边界
通过检索工具元信息动态加载定义，避免在会话起点注入海量工具 token。

## 二、原文为何选择该概念（问题-方案匹配）
原文实测展示大型 MCP 工具库中上下文占用和准确率双重改善。

## 三、局限性与失效条件（反例）
1. 增加检索步骤，低延迟场景可能受影响。
2. 工具描述质量差会直接伤害检索命中。
3. 检索器策略不当会引入“漏工具”风险。

## 四、替代路线（至少两条）与 trade-off
- **全量加载**：简单直观，但 token 成本高且干扰大。
- **人工白名单**：控制强，但扩展性不足。

## 五、理论推演与创新
可加入“任务类型->工具先验”模型，让首次检索更精准并减少二次搜索。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Context engineering》中的 just-in-time 机制是同一哲学。
- 直接引用目录：
- [Code execution with MCP: Building more efficient agents](../code-execution-with-mcp/00-code-execution-with-mcp-deep-dive.md)
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“Tool Search Tool：工具按需发现机制”定义了可观测指标？
- 我是否为“增加检索步骤，低延迟场景可能受影响。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Introducing advanced tool use on the Claude Developer Platform](https://www.anthropic.com/engineering/advanced-tool-use)
- 外部理论锚点：信息检索中的两阶段检索；缓存局部性原理
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
