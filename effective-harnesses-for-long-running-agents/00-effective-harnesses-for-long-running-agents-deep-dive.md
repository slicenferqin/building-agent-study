# 00. Effective Harnesses for Long-running Agents 精读：主精读

> 原文：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)

## 一、核心命题与关键结论（附来源）
1. 仅有 compaction 还不够，长任务失败往往来自“会话交接失真”。
2. 双阶段 harness（initializer + coding agent）能显著改善跨窗口持续推进能力。
3. 关键不在“更聪明”，在“留下可交接工件”：feature list、progress log、git commit、init.sh。
4. 增量推进 + 清洁收尾是长期自治的纪律基础。

## 二、机制拆解（What / Why / How）

### What：机制本体
1. initializer 首次搭建环境与任务台账，定义可验证目标列表。
2. coding agent 每轮只完成一个可验证增量，并更新工件。
3. 开局先“认路”（pwd、git log、progress、feature list）再动手。
4. 通过端到端测试防止“看起来完成、实际不可用”。

### Why：为什么在这类问题上有效
这篇文章针对的是“解决跨多上下文窗口长期任务的连续性与可交接问题。”。因此它关注的不是通用技巧堆叠，而是把失败概率最高的环节前置治理：先限制错误放大路径，再扩大自治与效率空间。

### How：落地时的执行顺序
建议按“最小闭环 -> 指标验证 -> 扩展能力”推进。每次扩展都必须同时回答三件事：
- 效果是否提升？
- 成本是否可控？
- 风险是否可回滚？

## 三、工程化映射（如何落到 agent 系统）
1. 项目层：把高层需求拆为 JSON 特性清单，持续更新 pass/fail 状态。
2. 执行层：每个会话有固定开场和收尾协议。
3. 质量层：提交前必须通过最小 e2e 回归，保持 clean state。
4. 协作层：把 agent 会话看作轮班工程师，交接文件即生产生命线。

## 四、误区与反模式（何时会失败）
1. 让 agent 一次性“冲完项目”，中途断窗导致半成品遗留。
2. 缺少进度工件，下一轮只能猜历史。
3. 只跑单元测试不做真实用户路径验证。
4. 结束时不提交与不总结，长期任务迅速退化。

## 五、跨文直接引用（不重复展开）
本篇涉及的共通知识，在以下目录已有完整论证。为避免重复，本文只保留应用层结论：
- [Effective context engineering for AI agents](../effective-context-engineering-for-ai-agents/00-effective-context-engineering-for-ai-agents-deep-dive.md)（概念索引：[`01-concept-context-as-finite-budget.md`](../effective-context-engineering-for-ai-agents/01-concept-context-as-finite-budget.md)）
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)（概念索引：[`01-concept-verify-first-loop.md`](../claude-code-best-practices-for-agentic-coding/01-concept-verify-first-loop.md)）
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)（概念索引：[`01-concept-overlapping-incident-diagnosis.md`](../a-postmortem-of-three-recent-issues/01-concept-overlapping-incident-diagnosis.md)）

## 六、理论推演与创新
1. 提出“会话交接工程学”：把交接质量作为核心能力，而非附属日志。
2. 提出“工件优先记忆”路线：比纯对话摘要更稳健。
3. 提出“会话启动脚本化”理念：把环境恢复成本降到最低。

## 七、案例化落地实验（建议）
- 阶段 A（建模）：把本篇命题写成 3-5 条可验证规则，并选一个真实任务做基线。
- 阶段 B（对照）：开启本篇方法与旧流程做对照，记录成功率、时延、token、重试次数。
- 阶段 C（固化）：把有效改动沉淀为工具描述、提示模板或评测用例，并纳入回归套件。

## 八、实践清单
- 是否已把“项目层：把高层需求拆为 JSON 特性清单，持续更新 pass/fail 状态。”落成可验证执行项？
- 是否已明确“执行层：每个会话有固定开场和收尾协议。”的触发条件和停止条件？
- 是否已对“让 agent 一次性“冲完项目”，中途断窗导致半成品遗留。”设置防呆机制？
- 是否已在评测中覆盖“缺少进度工件，下一轮只能猜历史。”对应失败路径？
- 是否已把本篇创新点转成下一轮实验假设（而非口号）？

## 九、本目录概念专题导航
- [`01-concept-initializer-coding-dual-loop.md`](./01-concept-initializer-coding-dual-loop.md)：Initializer/Coding 双循环架构
- [`02-concept-artifact-continuity.md`](./02-concept-artifact-continuity.md)：工件连续性（Artifact Continuity）
- [`03-concept-incremental-clean-state.md`](./03-concept-incremental-clean-state.md)：增量推进与 Clean State 纪律

## 十、关键来源
- 主来源：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- 关联来源：[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- 关联来源：[Claude Code: Best practices for agentic coding](https://code.claude.com/docs/en/best-practices)
- 关联来源：[A postmortem of three recent issues](https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues)
