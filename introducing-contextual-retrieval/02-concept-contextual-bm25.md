# 02. 概念专题：Contextual BM25：稀疏检索的再语境化

> 所属主文：[`00-introducing-contextual-retrieval-deep-dive.md`](./00-introducing-contextual-retrieval-deep-dive.md)
>
> 原始来源：[Introducing Contextual Retrieval](https://www.anthropic.com/engineering/contextual-retrieval)

## 一、概念定义与语义边界
将补充上下文后的 chunk 构建 BM25 索引，让关键词检索也具备语境定位能力。

## 二、原文为何选择该概念（问题-方案匹配）
仅靠向量检索可能错过关键词强约束场景，稀疏通道提供稳健补充。

## 三、局限性与失效条件（反例）
1. 关键词歧义在跨领域语料中依然存在。
2. 索引更新频率高时维护开销增大。
3. 多语言语料下分词策略会影响稳定性。

## 四、替代路线（至少两条）与 trade-off
- **仅 dense 检索**：语义强但在精确名词任务易漏召。
- **规则关键词检索**：可控强但语义泛化弱。

## 五、理论推演与创新
建议按任务类型动态调整稀疏/稠密权重，而非固定混合比例。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Advanced tool use》的按需工具发现可类比：都是先定位，再展开。
- 直接引用目录：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“Contextual BM25：稀疏检索的再语境化”定义了可观测指标？
- 我是否为“关键词歧义在跨领域语料中依然存在。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Introducing Contextual Retrieval](https://www.anthropic.com/engineering/contextual-retrieval)
- 外部理论锚点：BM25 概率检索模型；混合检索架构
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
