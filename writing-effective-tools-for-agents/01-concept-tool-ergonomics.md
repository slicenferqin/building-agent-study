# 01. 概念专题：工具人体工学（Tool Ergonomics）

> 所属主文：[`00-writing-effective-tools-for-agents-deep-dive.md`](./00-writing-effective-tools-for-agents-deep-dive.md)
>
> 原始来源：[Writing effective tools for agents — with agents](https://www.anthropic.com/engineering/writing-tools-for-agents)

## 一、概念定义与语义边界
强调工具应贴合模型的推理习惯和上下文限制，使正确调用成为低摩擦默认路径。

## 二、原文为何选择该概念（问题-方案匹配）
原文发现“人类觉得合理”的 API 并不一定“模型易用”，必须重新设计交互语义。

## 三、局限性与失效条件（反例）
1. 过度迎合单模型会损害跨模型迁移性。
2. 人体工学优化常与后端复用目标冲突。
3. 局部最优工具组合可能导致全局工具库复杂化。

## 四、替代路线（至少两条）与 trade-off
- **后端优先 API 映射**：工程成本低，但模型误用率高。
- **场景优先任务工具**：模型效果好，但设计和维护成本更高。

## 五、理论推演与创新
可引入“工具可学性评分”，在上线前量化模型首次正确调用概率、纠错步数和平均 token 成本。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Advanced tool use》中的 Tool Use Examples 形成前后衔接：一个管结构，一个管示例。
- 直接引用目录：
- [Building effective agents](../building-effective-agents/00-building-effective-agents-deep-dive.md)
- [Introducing advanced tool use on the Claude Developer Platform](../introducing-advanced-tool-use/00-introducing-advanced-tool-use-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“工具人体工学（Tool Ergonomics）”定义了可观测指标？
- 我是否为“过度迎合单模型会损害跨模型迁移性。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Writing effective tools for agents — with agents](https://www.anthropic.com/engineering/writing-tools-for-agents)
- 外部理论锚点：可用性工程（Usability Engineering）；认知负荷理论
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
