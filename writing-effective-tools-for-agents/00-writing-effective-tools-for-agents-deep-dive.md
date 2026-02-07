# 00. Writing Effective Tools for Agents 精读：主精读

> 原文：[Writing effective tools for agents — with agents](https://www.anthropic.com/engineering/writing-tools-for-agents)

## 一、核心命题与关键结论（附来源）
1. 工具开发的核心对象变了：不是给确定性程序员写 API，而是给非确定性代理写可用契约。
2. 工具质量不能靠直觉，必须依赖 eval 闭环；没有评测的工具优化等于手工玄学。
3. Claude 可参与工具反向优化：通过读轨迹改描述、改参数、改返回结构，实测能显著提效。
4. 工具设计的关键不是“多”，而是“高信号、低歧义、可组合”。

## 二、机制拆解（What / Why / How）

### What：机制本体
1. 先做可运行原型，再通过真实任务构建评测集，避免在纸面上优化。
2. 用任务级成功率、工具调用数、token 成本、错误率四维联合判断工具好坏。
3. 结合推理轨迹和 transcript 排查“模型没说出口但确实被困住”的摩擦点。
4. 用命名空间和工具语义边界降低错调与重复调度。

### Why：为什么在这类问题上有效
这篇文章针对的是“回答“工具怎么写才会被 agent 真正用好”而不是“勉强能调用”。”。因此它关注的不是通用技巧堆叠，而是把失败概率最高的环节前置治理：先限制错误放大路径，再扩大自治与效率空间。

### How：落地时的执行顺序
建议按“最小闭环 -> 指标验证 -> 扩展能力”推进。每次扩展都必须同时回答三件事：
- 效果是否提升？
- 成本是否可控？
- 风险是否可回滚？

## 三、工程化映射（如何落到 agent 系统）
1. 定义层：把工具当“任务单元”而非“数据库接口镜像”，减少中间态暴露。
2. 数据层：工具返回高信号字段，少返 UUID、冗余元数据，优先可行动信息。
3. 运行层：为常见复合动作做聚合工具，减少多次往返与上下文污染。
4. 优化层：让 agent 参与工具改写，形成“工具自进化”流水线。

## 四、误区与反模式（何时会失败）
1. 把已有 API 直接平移成工具，忽略 agent 的上下文预算。
2. 工具描述靠口语化想象，不写参数语义与约束。
3. 评测只看最终成功，不看路径成本与鲁棒性。
4. 只用开发者视角评估，不看模型真实使用轨迹。

## 五、跨文直接引用（不重复展开）
本篇涉及的共通知识，在以下目录已有完整论证。为避免重复，本文只保留应用层结论：
- [Building effective agents](../building-effective-agents/00-building-effective-agents-deep-dive.md)（概念索引：[`01-concept-workflow-vs-agent-boundary.md`](../building-effective-agents/01-concept-workflow-vs-agent-boundary.md)）
- [Introducing advanced tool use on the Claude Developer Platform](../introducing-advanced-tool-use/00-introducing-advanced-tool-use-deep-dive.md)（概念索引：[`01-concept-tool-search-tool.md`](../introducing-advanced-tool-use/01-concept-tool-search-tool.md)）
- [Demystifying evals for AI agents](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-grader-taxonomy.md`](../demystifying-evals-for-ai-agents/01-concept-grader-taxonomy.md)）

## 六、理论推演与创新
1. 提出“工具人体工学（Tool Ergonomics）”：工具越像人类可理解动作，模型越稳定。
2. 提出“描述即控制”：工具描述不是文案，而是策略路由器。
3. 提出“评测先行的工具设计”：先定义失败如何被发现，再定义工具如何成功。

## 七、案例化落地实验（建议）
- 阶段 A（建模）：把本篇命题写成 3-5 条可验证规则，并选一个真实任务做基线。
- 阶段 B（对照）：开启本篇方法与旧流程做对照，记录成功率、时延、token、重试次数。
- 阶段 C（固化）：把有效改动沉淀为工具描述、提示模板或评测用例，并纳入回归套件。

## 八、实践清单
- 是否已把“定义层：把工具当“任务单元”而非“数据库接口镜像”，减少中间态暴露。”落成可验证执行项？
- 是否已明确“数据层：工具返回高信号字段，少返 UUID、冗余元数据，优先可行动信息。”的触发条件和停止条件？
- 是否已对“把已有 API 直接平移成工具，忽略 agent 的上下文预算。”设置防呆机制？
- 是否已在评测中覆盖“工具描述靠口语化想象，不写参数语义与约束。”对应失败路径？
- 是否已把本篇创新点转成下一轮实验假设（而非口号）？

## 九、本目录概念专题导航
- [`01-concept-tool-ergonomics.md`](./01-concept-tool-ergonomics.md)：工具人体工学（Tool Ergonomics）
- [`02-concept-eval-driven-tool-iteration.md`](./02-concept-eval-driven-tool-iteration.md)：评测驱动工具迭代
- [`03-concept-namespacing-and-semantic-contract.md`](./03-concept-namespacing-and-semantic-contract.md)：命名空间与语义契约

## 十、关键来源
- 主来源：[Writing effective tools for agents — with agents](https://www.anthropic.com/engineering/writing-tools-for-agents)
- 关联来源：[Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)
- 关联来源：[Introducing advanced tool use on the Claude Developer Platform](https://www.anthropic.com/engineering/advanced-tool-use)
- 关联来源：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
