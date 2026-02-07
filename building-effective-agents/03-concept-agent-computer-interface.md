# 03. 概念专题：ACI（Agent-Computer Interface）作为一等公民

> 所属主文：[`00-building-effective-agents-deep-dive.md`](./00-building-effective-agents-deep-dive.md)
>
> 原始来源：[Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)

## 一、概念定义与语义边界
ACI 指 agent 与工具/环境交互时的可理解性、可执行性与可恢复性接口设计。

## 二、原文为何选择该概念（问题-方案匹配）
原文强调“工具文档就是提示词工程”，本质是把模型可用性前移到接口层。

## 三、局限性与失效条件（反例）
1. 过度追求通用接口会牺牲高频场景效率。
2. 只写 schema 不写语义边界，模型仍会误用。
3. 缺少错误分级与可恢复提示时，失败会级联。

## 四、替代路线（至少两条）与 trade-off
- **粗粒度万能工具**：开发快，但语义歧义大，易误调用。
- **细粒度专用工具**：控制精细，但工具数爆炸后选择困难。

## 五、理论推演与创新
建议引入“ACI 可观测契约”：每个工具返回结构化可解释字段（意图、影响面、可逆性）以支持自动审计。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Writing effective tools for agents》共同构成“工具工程学”主干。
- 直接引用目录：
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“ACI（Agent-Computer Interface）作为一等公民”定义了可观测指标？
- 我是否为“过度追求通用接口会牺牲高频场景效率。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)
- 外部理论锚点：Human-Computer Interaction 可供性理论；Goodhart 定律
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
