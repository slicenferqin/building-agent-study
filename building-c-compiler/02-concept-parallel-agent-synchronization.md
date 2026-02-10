# 02. 概念专题：并行代理同步协议（Parallel Agent Synchronization）

> 所属主文：[`00-building-c-compiler-deep-dive.md`](./00-building-c-compiler-deep-dive.md)
>
> 原始来源：[Building a C compiler with a team of parallel Claudes](https://www.anthropic.com/engineering/building-c-compiler)

## 一、概念定义与语义边界
`Parallel Agent Synchronization` 不是“多开几个代理窗口”，而是定义代理之间如何安全协同：
- 谁负责分解任务；
- 谁负责执行子任务；
- 谁负责合并与冲突裁决；
- 交接信息的最小结构是什么。

边界上要明确：并行提高的是吞吐，不保证自动一致性。没有同步协议，并行只会把错误放大得更快。

## 二、原文为何选择该概念（问题-方案匹配）
编译器天然具备可并行子问题（前端、优化、后端、测试等），因此并行代理理论上可显著提速。但编译器同样存在高耦合不变量（类型、调用约定、寄存器约束）。

原文选择并行团队模式，是因为它能够在“可分解子系统”中释放速度，同时通过同步机制控制耦合风险。换言之，这是一个“有条件成立”的并行收益模型。

## 三、局限性与失效条件（反例）
1. 子任务切分过细会产生高通信开销，吞吐收益被同步成本抵消。
2. 子任务切分过粗会导致冲突合并困难，后期集成风险上升。
3. 如果没有统一不变量清单（例如 IR 约束），局部最优改动会破坏全局一致性。
4. 如果主协调代理缺少裁决机制，冲突会被反复转发而无法收敛。

## 四、替代路线（至少两条）与 trade-off
- **路线 A：单代理深推理**：一致性高，但在超大任务上速度和覆盖不足。
- **路线 B：静态流水线工作流**：确定性好，但面对新问题时弹性有限。
- **路线 C：并行代理 + 同步协议（本文路线）**：速度潜力高，但需要额外治理设计。

## 五、理论推演与创新
建议引入“类型化交接契约（Typed Handoff Contract）”：每个子代理输出固定字段（输入前提、变更范围、不变量影响、验证状态、回滚方案）。这能把“协作靠口头默契”升级为“协作靠结构化接口”，显著提升并行系统可调试性。

进一步推演，可把并行代理系统视作“分布式工程组织”：吞吐由并行度决定，稳定由一致性协议决定。二者缺一不可。

## 六、与其他博客概念关联（去重引用）
- 本文只讨论“编译器构建”场景下的同步协议，不重复多代理通用方法论。
- 关联说明：该概念把多代理研究系统中的角色分工，映射到高约束代码工程任务。
- 直接引用目录：
  - [`../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md`](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)
  - [`../multi-agent-research-system/01-concept-lead-subagent-architecture.md`](../multi-agent-research-system/01-concept-lead-subagent-architecture.md)

## 七、实战检查清单
- [ ] 我是否给每个代理定义了不可重叠的主责边界？
- [ ] 我是否规定了合并前必须通过的最小验证集？
- [ ] 我是否有冲突升级路径（谁裁决、按什么规则裁决）？
- [ ] 我是否跟踪了并行带来的真实收益，而非只看表面忙碌度？
- [ ] 我是否保留了“降级到单代理/小并行”的切换策略？

## 八、来源与外部理论
- 主来源：[Building a C compiler with a team of parallel Claudes](https://www.anthropic.com/engineering/building-c-compiler)
- 外部理论锚点：分布式系统一致性协议；组织设计中的职责分离
- 说明：外部锚点用于建立可迁移框架，不替代主来源结论。
