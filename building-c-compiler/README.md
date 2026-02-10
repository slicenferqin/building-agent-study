# Building a C Compiler 精读 导读

> 原文：[Building a C compiler with a team of parallel Claudes](https://www.anthropic.com/engineering/building-c-compiler)
>
> 批次：新增

## 本篇定位
这篇文章回答的是一个很硬的问题：**当任务跨度达到“月级迭代 + 多子系统协作 + 强正确性约束”时，Agent 系统到底能不能稳定完成真实工程产出**。

## 建议阅读顺序
1. [`00-building-c-compiler-deep-dive.md`](./00-building-c-compiler-deep-dive.md)：主精读，先把整体实验结构与关键结论吃透。
2. [`01-concept-long-running-loop-harness.md`](./01-concept-long-running-loop-harness.md)：长程闭环（long-running loop harness）如何保证连续性。
3. [`02-concept-parallel-agent-synchronization.md`](./02-concept-parallel-agent-synchronization.md)：并行代理协同（parallel-agent synchronization）如何避免“多而乱”。
4. [`03-concept-oracle-guided-evaluation.md`](./03-concept-oracle-guided-evaluation.md)：Oracle 驱动评测（oracle-guided evaluation）如何把“能跑”变成“可证据化正确”。

## 跨文直接引用（去重）
以下能力在其他目录已有完整展开，本目录只做编译器场景化映射：
- 长任务会话治理与工件交接：[`../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md`](../effective-harnesses-for-long-running-agents/00-effective-harnesses-for-long-running-agents-deep-dive.md)
- 多代理角色编排与 effort scaling：[`../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md`](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)
- 系统级评测防线设计：[`../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md`](../demystifying-evals-for-ai-agents/00-demystifying-evals-for-ai-agents-deep-dive.md)

## 目录结构说明
- 主文：`00-building-c-compiler-deep-dive.md`
- 概念专题：3 篇，采用“关键概念单独建模”的自适应结构。
- 引用规范：关键结论引用原文；共通知识通过跨文链接引用，避免重复论证。
