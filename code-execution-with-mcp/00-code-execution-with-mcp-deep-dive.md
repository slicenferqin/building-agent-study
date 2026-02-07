# 00. Code Execution with MCP 精读：主精读

> 原文：[Code execution with MCP: Building more efficient agents](https://www.anthropic.com/engineering/code-execution-with-mcp)

## 一、核心命题与关键结论（附来源）
1. MCP 工具规模化后，定义与中间结果会吞噬大量上下文，成为成本与准确率瓶颈。
2. 代码执行模式通过按需加载与就地处理，把数据处理从模型上下文转移到执行环境。
3. 该模式不仅优化 token，还能增强隐私控制与状态持久化。
4. 收益建立在强沙箱与治理基础上，否则会引入新的安全负担。

## 二、机制拆解（What / Why / How）

### What：机制本体
1. 把 MCP 工具映射为代码 API，模型按文件系统探索并调用。
2. 在执行环境中完成过滤、聚合、循环、条件分支，只回传必要摘要。
3. 通过数据标记与 tokenization 机制减少敏感信息进入模型上下文。
4. 借助文件系统实现中间状态持久化，支持可恢复工作流。

### Why：为什么在这类问题上有效
这篇文章针对的是“从“模型逐次工具调用”迁移到“模型写代码编排工具”，提升效率与控制力。”。因此它关注的不是通用技巧堆叠，而是把失败概率最高的环节前置治理：先限制错误放大路径，再扩大自治与效率空间。

### How：落地时的执行顺序
建议按“最小闭环 -> 指标验证 -> 扩展能力”推进。每次扩展都必须同时回答三件事：
- 效果是否提升？
- 成本是否可控？
- 风险是否可回滚？

## 三、工程化映射（如何落到 agent 系统）
1. 工具层：为高频数据密集任务优先启用代码编排模式。
2. 安全层：配套最小权限沙箱、网络限制、资源配额和审计日志。
3. 性能层：监控 token 节省、时延变化和错误分布。
4. 产品层：将“何时进入代码模式”显式规则化。

## 四、误区与反模式（何时会失败）
1. 只看 token 降低，忽略执行环境安全成本。
2. 工具返回格式不稳定，导致代码解析脆弱。
3. 状态文件缺少生命周期管理，积累技术债。
4. 误把所有任务都代码化，造成不必要复杂度。

## 五、跨文直接引用（不重复展开）
本篇涉及的共通知识，在以下目录已有完整论证。为避免重复，本文只保留应用层结论：
- [Introducing advanced tool use on the Claude Developer Platform](../introducing-advanced-tool-use/00-introducing-advanced-tool-use-deep-dive.md)（概念索引：[`01-concept-tool-search-tool.md`](../introducing-advanced-tool-use/01-concept-tool-search-tool.md)）
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)（概念索引：[`01-concept-dual-isolation.md`](../beyond-permission-prompts-claude-code-sandboxing/01-concept-dual-isolation.md)）
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)（概念索引：[`01-concept-tool-ergonomics.md`](../writing-effective-tools-for-agents/01-concept-tool-ergonomics.md)）

## 六、理论推演与创新
1. 提出“模型写策略，代码跑流程”的职责分离范式。
2. 提出“上下文外计算”思路：把大部分机械处理迁移出语言模型。
3. 提出“数据流治理先于智能编排”：先管数据边界，再谈自动化规模。

## 七、案例化落地实验（建议）
- 阶段 A（建模）：把本篇命题写成 3-5 条可验证规则，并选一个真实任务做基线。
- 阶段 B（对照）：开启本篇方法与旧流程做对照，记录成功率、时延、token、重试次数。
- 阶段 C（固化）：把有效改动沉淀为工具描述、提示模板或评测用例，并纳入回归套件。

## 八、实践清单
- 是否已把“工具层：为高频数据密集任务优先启用代码编排模式。”落成可验证执行项？
- 是否已明确“安全层：配套最小权限沙箱、网络限制、资源配额和审计日志。”的触发条件和停止条件？
- 是否已对“只看 token 降低，忽略执行环境安全成本。”设置防呆机制？
- 是否已在评测中覆盖“工具返回格式不稳定，导致代码解析脆弱。”对应失败路径？
- 是否已把本篇创新点转成下一轮实验假设（而非口号）？

## 九、本目录概念专题导航
- [`01-concept-code-first-tool-orchestration.md`](./01-concept-code-first-tool-orchestration.md)：代码优先工具编排
- [`02-concept-privacy-preserving-data-flow.md`](./02-concept-privacy-preserving-data-flow.md)：隐私保留的数据流控制
- [`03-concept-stateful-execution-and-resume.md`](./03-concept-stateful-execution-and-resume.md)：状态化执行与可恢复工作流

## 十、关键来源
- 主来源：[Code execution with MCP: Building more efficient agents](https://www.anthropic.com/engineering/code-execution-with-mcp)
- 关联来源：[Introducing advanced tool use on the Claude Developer Platform](https://www.anthropic.com/engineering/advanced-tool-use)
- 关联来源：[Beyond permission prompts: making Claude Code more secure and autonomous](https://www.anthropic.com/engineering/claude-code-sandboxing)
- 关联来源：[Writing effective tools for agents — with agents](https://www.anthropic.com/engineering/writing-tools-for-agents)
