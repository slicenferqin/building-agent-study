# 01. 概念专题：长程闭环外壳（Long-running Loop Harness）

> 所属主文：[`00-building-c-compiler-deep-dive.md`](./00-building-c-compiler-deep-dive.md)
>
> 原始来源：[Building a C compiler with a team of parallel Claudes](https://www.anthropic.com/engineering/building-c-compiler)

## 一、概念定义与语义边界
`Long-running Loop Harness` 指的是：在跨大量会话、跨多阶段任务中，为代理提供稳定的“执行-验证-交接”框架。它不是单个 prompt，也不是单个脚本，而是一套持续运行协议：如何恢复上下文、如何记录状态、如何控制风险、如何交接下一轮。

语义边界要划清：
- Harness 负责“可持续执行”；
- 模型负责“局部决策与生成”；
- 评测负责“是否过线”。

把三者混在一起，会导致定位失败原因时无从下手。

## 二、原文为何选择该概念（问题-方案匹配）
C 编译器构建不是一天能做完的任务，而且每次改动都可能破坏系统不变量。原文选择 Harness，是因为它能把“上下文窗口限制”与“长任务连续性”拆开处理：窗口可以轮换，但任务状态必须可恢复。

换句话说，Harness 解决的是“记忆与秩序”问题。没有它，多代理系统再聪明，也会在长周期中丢失任务主线。

## 三、局限性与失效条件（反例）
1. 如果工件协议不统一（同一状态多种格式），Harness 会退化成噪声仓库，恢复成本反而更高。
2. 如果只记录“做了什么”而不记录“为什么这样做”，后续会话会重复探索，造成隐性成本。
3. 如果没有明确停止条件，长程循环容易被“局部改进冲动”拖入无限迭代。
4. 如果验证信号太弱（只看能跑，不看正确），Harness 只能稳定地产生错误。

## 四、替代路线（至少两条）与 trade-off
- **路线 A：超长单会话策略**：实现简单，但随着上下文膨胀会出现注意力衰减，长期可靠性差。
- **路线 B：外部工作流编排器主导**：流程更可控，但灵活探索能力下降，适配新问题较慢。
- **路线 C：Harness + 工件化记忆（本文路线）**：工程复杂度较高，但在长期任务中兼顾了连续性与探索性。

## 五、理论推演与创新
可进一步引入“可回放 Harness”机制：每轮会话自动输出结构化事件日志（决策输入、动作、验证结果、异常标签），必要时可按时间回放并定位分叉点。这样做的意义是把“长程代理行为”从黑盒会话升级为可审计系统。

进一步的理论价值在于：它把 Agent 系统从“生成范式”推进到“过程范式”。当过程可回放、可比较、可回滚时，工程治理能力才真正建立。

## 六、与其他博客概念关联（去重引用）
- 本文只展开编译器场景下的长程外壳，不重复复述通用长任务治理全景。
- 关联说明：本概念是“上下文工程 -> 多代理协作 -> 评测闭环”的底层承载层。
- 直接引用目录：
  - [`../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md`](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)
  - [`../claude-code-best-practices-for-agentic-coding/02-concept-context-management-discipline.md`](../claude-code-best-practices-for-agentic-coding/02-concept-context-management-discipline.md)

## 七、实战检查清单
- [ ] 我是否定义了固定的会话开场/收尾协议？
- [ ] 我是否有可机读的进度工件，而非仅自然语言摘要？
- [ ] 我是否记录了关键决策的“理由字段”，支持后续回放？
- [ ] 我是否为会话中断设计了恢复路径（resume）并实际演练？
- [ ] 我是否把失败类型结构化归因，而不只记录“失败了”？

## 八、来源与外部理论
- 主来源：[Building a C compiler with a team of parallel Claudes](https://www.anthropic.com/engineering/building-c-compiler)
- 外部理论锚点：事件溯源（Event Sourcing）；持续集成中的可追溯性工程
- 说明：外部锚点用于扩展迁移能力，不替代主来源结论。
