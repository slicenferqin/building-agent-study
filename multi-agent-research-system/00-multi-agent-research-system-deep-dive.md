# 00. How We Built Our Multi-agent Research System 精读：主精读

> 原文：[How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)

## 一、核心命题与关键结论（附来源）
1. 多代理的核心价值不是“更像组织图”，而是“扩展有效 token 使用能力”。
2. lead agent + subagents + citation agent 的流水线，把探索、综合、归因拆开治理。
3. 资源分配规则（子代理数量、工具调用预算）决定了系统是否高效。
4. 多代理不是通用解：并行性不足或强共享上下文任务未必适配。

## 二、机制拆解（What / Why / How）

### What：机制本体
1. 主代理做问题分解与策略规划，子代理并行探索不同维度。
2. 子代理执行搜索-评估-再搜索的 interleaved 循环，返回压缩摘要。
3. 最终由 citation agent 做证据定位，降低“结论-来源”错配。
4. 通过 prompt 规则控制代理努力程度，避免过度搜索。

### Why：为什么在这类问题上有效
这篇文章针对的是“解释多代理系统为何在高价值研究任务上显著优于单代理，以及代价何在。”。因此它关注的不是通用技巧堆叠，而是把失败概率最高的环节前置治理：先限制错误放大路径，再扩大自治与效率空间。

### How：落地时的执行顺序
建议按“最小闭环 -> 指标验证 -> 扩展能力”推进。每次扩展都必须同时回答三件事：
- 效果是否提升？
- 成本是否可控？
- 风险是否可回滚？

## 三、工程化映射（如何落到 agent 系统）
1. 任务分层：先判断是否属于“高并行研究任务”，再决定是否启用多代理。
2. 预算分层：按问题复杂度映射子代理数和每代理调用上限。
3. 评测分层：结果质量、引用准确、工具效率三线并行评价。
4. 运维分层：把同步瓶颈、协作冲突、成本波动纳入常态监控。

## 四、误区与反模式（何时会失败）
1. 子代理分工描述不清，导致重复劳动。
2. 主代理过度 micromanage，扼杀并行收益。
3. 没有 effort scaling 规则，简单问题也烧大量 token。
4. 把路径正确性当硬约束，错杀创造性正确解。

## 五、跨文直接引用（不重复展开）
本篇涉及的共通知识，在以下目录已有完整论证。为避免重复，本文只保留应用层结论：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-context-as-finite-budget.md`](../effective-context-engineering-for-ai-agents/01-concept-context-as-finite-budget.md)）
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-grader-taxonomy.md`](../demystifying-evals-for-ai-agents/01-concept-grader-taxonomy.md)）
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)（概念索引：[`01-concept-initializer-coding-dual-loop.md`](../effective-harnesses-for-long-running-agents/01-concept-initializer-coding-dual-loop.md)）

## 六、理论推演与创新
1. 提出“token 扩容架构”视角：多代理本质是并行上下文窗口利用。
2. 提出“研究努力配额”机制：把智能系统的资源分配从隐式变显式。
3. 提出“协作框架式提示词”：与其硬性命令，不如定义协作协议。

## 七、案例化落地实验（建议）
- 阶段 A（建模）：把本篇命题写成 3-5 条可验证规则，并选一个真实任务做基线。
- 阶段 B（对照）：开启本篇方法与旧流程做对照，记录成功率、时延、token、重试次数。
- 阶段 C（固化）：把有效改动沉淀为工具描述、提示模板或评测用例，并纳入回归套件。

## 八、实践清单
- 是否已把“任务分层：先判断是否属于“高并行研究任务”，再决定是否启用多代理。”落成可验证执行项？
- 是否已明确“预算分层：按问题复杂度映射子代理数和每代理调用上限。”的触发条件和停止条件？
- 是否已对“子代理分工描述不清，导致重复劳动。”设置防呆机制？
- 是否已在评测中覆盖“主代理过度 micromanage，扼杀并行收益。”对应失败路径？
- 是否已把本篇创新点转成下一轮实验假设（而非口号）？

## 九、本目录概念专题导航
- [`01-concept-lead-subagent-architecture.md`](./01-concept-lead-subagent-architecture.md)：Lead/Subagent/Citation 三层结构
- [`02-concept-effort-scaling-heuristics.md`](./02-concept-effort-scaling-heuristics.md)：努力规模化启发式（Effort Scaling）
- [`03-concept-emergent-coordination-evals.md`](./03-concept-emergent-coordination-evals.md)：涌现协作行为与评测方法

## 十、关键来源
- 主来源：[How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)
- 关联来源：[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- 关联来源：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
- 关联来源：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
