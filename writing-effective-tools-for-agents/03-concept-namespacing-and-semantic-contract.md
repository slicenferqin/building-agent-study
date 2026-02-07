# 03. 概念专题：命名空间与语义契约

> 所属主文：[`00-writing-effective-tools-for-agents-deep-dive.md`](./00-writing-effective-tools-for-agents-deep-dive.md)
>
> 原始来源：[Writing effective tools for agents — with agents](https://www.anthropic.com/engineering/writing-tools-for-agents)

## 一、概念定义与语义边界
通过一致命名和语义边界让模型快速判别工具职责，减少混淆调用。

## 二、原文为何选择该概念（问题-方案匹配）
在 MCP 多工具环境中，命名就是一级路由信号，命名混乱会直接伤害成功率。

## 三、局限性与失效条件（反例）
1. 命名过细会导致长名称和认知噪音。
2. 命名稳定性与版本演化存在张力。
3. 不同团队命名风格不一致会削弱整体可发现性。

## 四、替代路线（至少两条）与 trade-off
- **服务前缀命名**：定位快，但跨服务任务可能碎片化。
- **资源语义命名**：可读性强，但跨资源复合动作难表达。

## 五、理论推演与创新
可引入“语义别名层”：对历史命名做兼容映射，同时保持对模型可读的新命名主干。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Code execution with MCP》中的按需加载策略结合后，可形成“可发现 + 可执行”的双优化。
- 直接引用目录：
- [Building effective agents](../building-effective-agents/00-building-effective-agents-deep-dive.md)
- [Introducing advanced tool use on the Claude Developer Platform](../introducing-advanced-tool-use/00-introducing-advanced-tool-use-deep-dive.md)
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)

## 七、实战检查清单
- 我是否给“命名空间与语义契约”定义了可观测指标？
- 我是否为“命名过细会导致长名称和认知噪音。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Writing effective tools for agents — with agents](https://www.anthropic.com/engineering/writing-tools-for-agents)
- 外部理论锚点：领域驱动设计中的统一语言；信息架构（IA）
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
