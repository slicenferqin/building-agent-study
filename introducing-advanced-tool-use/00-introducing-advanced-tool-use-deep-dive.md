# 00. Introducing Advanced Tool Use 精读：主精读

> 原文：[Introducing advanced tool use on the Claude Developer Platform](https://www.anthropic.com/engineering/advanced-tool-use)

## 一、核心命题与关键结论（附来源）
1. 高级工具使用不是新增三个功能，而是工具规模化时代的系统重构。
2. Tool Search Tool 把工具定义从“全量预载”改为“按需显式加载”，显著减少上下文占用。
3. Programmatic Tool Calling 让模型用代码编排工具，减少中间结果污染并提升控制流能力。
4. Tool Use Examples 用行为示例补齐 schema 语义盲区，提升参数正确率。

## 二、机制拆解（What / Why / How）

### What：机制本体
1. 通过 defer_loading 实现工具惰性加载，提升缓存友好性。
2. 通过 allowed_callers 把工具授权给代码执行环境，形成程序化调用路径。
3. 通过 input_examples 编码“正确调用习惯”，降低复杂参数错误。
4. 按瓶颈分层启用三能力，避免一开始堆满复杂度。

### Why：为什么在这类问题上有效
这篇文章针对的是“在大规模工具库条件下，解决“找得到、调得对、跑得动”三连问题。”。因此它关注的不是通用技巧堆叠，而是把失败概率最高的环节前置治理：先限制错误放大路径，再扩大自治与效率空间。

### How：落地时的执行顺序
建议按“最小闭环 -> 指标验证 -> 扩展能力”推进。每次扩展都必须同时回答三件事：
- 效果是否提升？
- 成本是否可控？
- 风险是否可回滚？

## 三、工程化映射（如何落到 agent 系统）
1. 发现层：优先优化工具命名与描述，让 search 命中更稳定。
2. 执行层：把循环、条件、聚合放入代码执行环境，减少模型往返。
3. 治理层：记录每次工具发现与调用轨迹，定位误调用模式。
4. 经济层：按任务价值决定是否开启全部高级能力。

## 四、误区与反模式（何时会失败）
1. 把所有工具都设为延迟加载，导致高频核心工具反而增延迟。
2. 程序化调用中返回格式不清，模型解析失败。
3. 示例过多过长，反而吃掉上下文收益。
4. 忽略权限边界，代码执行可调用范围过宽。

## 五、跨文直接引用（不重复展开）
本篇涉及的共通知识，在以下目录已有完整论证。为避免重复，本文只保留应用层结论：
- [Code execution with MCP: Building more efficient agents](../code-execution-with-mcp/00-code-execution-with-mcp-deep-dive.md)（概念索引：[`01-concept-code-first-tool-orchestration.md`](../code-execution-with-mcp/01-concept-code-first-tool-orchestration.md)）
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)（概念索引：[`01-concept-tool-ergonomics.md`](../writing-effective-tools-for-agents/01-concept-tool-ergonomics.md)）
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-context-as-finite-budget.md`](../effective-context-engineering-for-ai-agents/01-concept-context-as-finite-budget.md)）

## 六、理论推演与创新
1. 提出“工具操作系统化”视角：工具从函数集合演化为可检索、可编排、可学习的运行时。
2. 提出“三层瓶颈诊断法”：发现瓶颈→执行瓶颈→调用精度瓶颈，逐层治理。
3. 提出“示例即协议补丁”：当 schema 表达力不足时，用示例承载隐含规则。

## 七、案例化落地实验（建议）
- 阶段 A（建模）：把本篇命题写成 3-5 条可验证规则，并选一个真实任务做基线。
- 阶段 B（对照）：开启本篇方法与旧流程做对照，记录成功率、时延、token、重试次数。
- 阶段 C（固化）：把有效改动沉淀为工具描述、提示模板或评测用例，并纳入回归套件。

## 八、实践清单
- 是否已把“发现层：优先优化工具命名与描述，让 search 命中更稳定。”落成可验证执行项？
- 是否已明确“执行层：把循环、条件、聚合放入代码执行环境，减少模型往返。”的触发条件和停止条件？
- 是否已对“把所有工具都设为延迟加载，导致高频核心工具反而增延迟。”设置防呆机制？
- 是否已在评测中覆盖“程序化调用中返回格式不清，模型解析失败。”对应失败路径？
- 是否已把本篇创新点转成下一轮实验假设（而非口号）？

## 九、本目录概念专题导航
- [`01-concept-tool-search-tool.md`](./01-concept-tool-search-tool.md)：Tool Search Tool：工具按需发现机制
- [`02-concept-programmatic-tool-calling.md`](./02-concept-programmatic-tool-calling.md)：Programmatic Tool Calling：代码化工具编排
- [`03-concept-tool-use-examples.md`](./03-concept-tool-use-examples.md)：Tool Use Examples：示例化调用协议

## 十、关键来源
- 主来源：[Introducing advanced tool use on the Claude Developer Platform](https://www.anthropic.com/engineering/advanced-tool-use)
- 关联来源：[Code execution with MCP: Building more efficient agents](https://www.anthropic.com/engineering/code-execution-with-mcp)
- 关联来源：[Writing effective tools for agents — with agents](https://www.anthropic.com/engineering/writing-tools-for-agents)
- 关联来源：[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
