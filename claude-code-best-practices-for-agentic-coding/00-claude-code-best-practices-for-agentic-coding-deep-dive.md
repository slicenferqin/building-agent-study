# 00. Claude Code Best Practices 精读：主精读

> 原文：[Claude Code: Best practices for agentic coding](https://code.claude.com/docs/en/best-practices)

## 一、核心命题与关键结论（附来源）
1. 最高杠杆动作是“给验证手段”：测试、截图、预期输出决定 agent 成败。
2. 推荐工作流是 Explore → Plan → Implement → Commit，先分离认知再执行。
3. 上下文管理是第一资源管理问题，`/clear` 与 `/compact` 是质量保障工具。
4. 自治能力应与沙箱和权限策略绑定，不应盲目跳过权限检查。

## 二、机制拆解（What / Why / How）

### What：机制本体
1. 通过 CLAUDE.md 提供稳定项目约束，减少重复口头指令。
2. 用 skills/subagents 把高频流程模块化，降低单次会话负荷。
3. 利用 checkpoint、resume、多会话并行提升复杂任务推进效率。
4. 识别并规避典型失败模式：任务串台、反复纠错、说明文件过长。

### Why：为什么在这类问题上有效
这篇文章针对的是“把“如何高效与安全地用 coding agent”从经验贴整理为可操作方法论。”。因此它关注的不是通用技巧堆叠，而是把失败概率最高的环节前置治理：先限制错误放大路径，再扩大自治与效率空间。

### How：落地时的执行顺序
建议按“最小闭环 -> 指标验证 -> 扩展能力”推进。每次扩展都必须同时回答三件事：
- 效果是否提升？
- 成本是否可控？
- 风险是否可回滚？

## 三、工程化映射（如何落到 agent 系统）
1. 个人效率：每次任务先写可验证验收条件，再给 agent 目标。
2. 团队协作：把 CLAUDE.md 纳入版本管理并持续瘦身。
3. 安全治理：高自治模式必须配套沙箱边界。
4. 规模化执行：headless + 并行会话用于批量任务，但要控制上下文污染。

## 四、误区与反模式（何时会失败）
1. 模糊指令导致反复返工。
2. 把多个无关任务塞进一个会话。
3. CLAUDE.md 过长导致关键规则被淹没。
4. 为了速度直接开全权限，忽略潜在注入风险。

## 五、跨文直接引用（不重复展开）
本篇涉及的共通知识，在以下目录已有完整论证。为避免重复，本文只保留应用层结论：
- [Equipping agents for the real world with Agent Skills](../equipping-agents-for-the-real-world-with-agent-skills/00-equipping-agents-for-the-real-world-with-agent-skills-deep-dive.md)（概念索引：[`01-concept-progressive-disclosure.md`](../equipping-agents-for-the-real-world-with-agent-skills/01-concept-progressive-disclosure.md)）
- [Effective harnesses for long-running agents](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)（概念索引：[`01-concept-initializer-coding-dual-loop.md`](../effective-harnesses-for-long-running-agents/01-concept-initializer-coding-dual-loop.md)）
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)（概念索引：[`01-concept-dual-isolation.md`](../beyond-permission-prompts-claude-code-sandboxing/01-concept-dual-isolation.md)）

## 六、理论推演与创新
1. 提出“验证先行协作法”：把 agent 从“猜需求”改为“对齐验收”。
2. 提出“上下文纪律化”：会话管理本身就是工程实践。
3. 提出“技能化工作流”：把个人经验积累为可共享能力包。

## 七、案例化落地实验（建议）
- 阶段 A（建模）：把本篇命题写成 3-5 条可验证规则，并选一个真实任务做基线。
- 阶段 B（对照）：开启本篇方法与旧流程做对照，记录成功率、时延、token、重试次数。
- 阶段 C（固化）：把有效改动沉淀为工具描述、提示模板或评测用例，并纳入回归套件。

## 八、实践清单
- 是否已把“个人效率：每次任务先写可验证验收条件，再给 agent 目标。”落成可验证执行项？
- 是否已明确“团队协作：把 CLAUDE.md 纳入版本管理并持续瘦身。”的触发条件和停止条件？
- 是否已对“模糊指令导致反复返工。”设置防呆机制？
- 是否已在评测中覆盖“把多个无关任务塞进一个会话。”对应失败路径？
- 是否已把本篇创新点转成下一轮实验假设（而非口号）？

## 九、本目录概念专题导航
- [`01-concept-verify-first-loop.md`](./01-concept-verify-first-loop.md)：Verify-first 协作闭环
- [`02-concept-context-management-discipline.md`](./02-concept-context-management-discipline.md)：上下文管理纪律
- [`03-concept-safe-autonomous-mode.md`](./03-concept-safe-autonomous-mode.md)：Safe Autonomous Mode 的边界实践

## 十、关键来源
- 主来源：[Claude Code: Best practices for agentic coding](https://code.claude.com/docs/en/best-practices)
- 关联来源：[Equipping agents for the real world with Agent Skills](https://claude.com/blog/equipping-agents-for-the-real-world-with-agent-skills)
- 关联来源：[Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- 关联来源：[Beyond permission prompts: making Claude Code more secure and autonomous](https://www.anthropic.com/engineering/claude-code-sandboxing)
