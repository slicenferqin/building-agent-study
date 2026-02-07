# 00. Demystifying Evals for AI Agents 精读：主精读

> 原文：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)

## 一、核心命题与关键结论（附来源）
1. 没有 eval 的团队会陷入“线上出事-人工救火-再次回归”的反应式循环。
2. agent eval 的难点在于多步与多路径：同一输入可能存在多种正确轨迹。
3. 代码评分、模型评分、人类评分需要分层组合，而非单点依赖。
4. 评测不是一次建设，而是 capability→regression→生产监控的演进体系。

## 二、机制拆解（What / Why / How）

### What：机制本体
1. 定义任务与 grader：输入、环境、输出、判分逻辑四要素。
2. 区分能力评测与回归评测，前者找上限，后者保底线。
3. 用 LLM-as-judge 扩展开放任务评分，但要持续人类校准。
4. 将自动评测、线上监控、A/B、人工审阅组合成“瑞士奶酪”防线。

### Why：为什么在这类问题上有效
这篇文章针对的是“把“评测”从上线前附属动作，升级为 agent 生命周期主干系统。”。因此它关注的不是通用技巧堆叠，而是把失败概率最高的环节前置治理：先限制错误放大路径，再扩大自治与效率空间。

### How：落地时的执行顺序
建议按“最小闭环 -> 指标验证 -> 扩展能力”推进。每次扩展都必须同时回答三件事：
- 效果是否提升？
- 成本是否可控？
- 风险是否可回滚？

## 三、工程化映射（如何落到 agent 系统）
1. 研发流程：每次模型或提示词变更都自动触发最小回归套件。
2. 产品流程：把用户投诉样例自动转化为新增 eval case。
3. 数据流程：保留可审阅 transcript 视图，避免“看分不看因”。
4. 组织流程：让产品、研究、工程共享同一评测语言。

## 四、误区与反模式（何时会失败）
1. 追求“完美大评测”导致长期不开工。
2. 评分器过刚，惩罚了合理但非预设路径。
3. 只看离线分数，忽视线上分布漂移。
4. 不读 transcript，把评测当黑箱数值。

## 五、跨文直接引用（不重复展开）
本篇涉及的共通知识，在以下目录已有完整论证。为避免重复，本文只保留应用层结论：
- [Building effective agents](../building-effective-agents/00-building-effective-agents-deep-dive.md)（概念索引：[`01-concept-workflow-vs-agent-boundary.md`](../building-effective-agents/01-concept-workflow-vs-agent-boundary.md)）
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)（概念索引：[`01-concept-lead-subagent-architecture.md`](../multi-agent-research-system/01-concept-lead-subagent-architecture.md)）
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)（概念索引：[`01-concept-overlapping-incident-diagnosis.md`](../a-postmortem-of-three-recent-issues/01-concept-overlapping-incident-diagnosis.md)）

## 六、理论推演与创新
1. 提出“评测即产品规格”：把模糊期望转成可执行判分逻辑。
2. 提出“失败样例资本化”：每次故障都应沉淀为未来护城河。
3. 提出“多层防线思想”：单一指标永远不够，组合防护才稳。

## 七、案例化落地实验（建议）
- 阶段 A（建模）：把本篇命题写成 3-5 条可验证规则，并选一个真实任务做基线。
- 阶段 B（对照）：开启本篇方法与旧流程做对照，记录成功率、时延、token、重试次数。
- 阶段 C（固化）：把有效改动沉淀为工具描述、提示模板或评测用例，并纳入回归套件。

## 八、实践清单
- 是否已把“研发流程：每次模型或提示词变更都自动触发最小回归套件。”落成可验证执行项？
- 是否已明确“产品流程：把用户投诉样例自动转化为新增 eval case。”的触发条件和停止条件？
- 是否已对“追求“完美大评测”导致长期不开工。”设置防呆机制？
- 是否已在评测中覆盖“评分器过刚，惩罚了合理但非预设路径。”对应失败路径？
- 是否已把本篇创新点转成下一轮实验假设（而非口号）？

## 九、本目录概念专题导航
- [`01-concept-grader-taxonomy.md`](./01-concept-grader-taxonomy.md)：评分器三分法：代码 / 模型 / 人类
- [`02-concept-capability-and-regression-lifecycle.md`](./02-concept-capability-and-regression-lifecycle.md)：能力评测与回归评测生命周期
- [`03-concept-swiss-cheese-evaluation-stack.md`](./03-concept-swiss-cheese-evaluation-stack.md)：瑞士奶酪式多层评估防线

## 十、关键来源
- 主来源：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
- 关联来源：[Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)
- 关联来源：[How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)
- 关联来源：[A postmortem of three recent issues](https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues)
