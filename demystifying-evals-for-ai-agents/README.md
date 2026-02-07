# Demystifying Evals for AI Agents 精读 导读

> 原文：[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
>
> 批次：第二批（系统化工程、评测、安全与复盘）

## 本篇定位
把“评测”从上线前附属动作，升级为 agent 生命周期主干系统。

## 建议阅读顺序
1. [`00-demystifying-evals-for-ai-agents-deep-dive.md`](./00-demystifying-evals-for-ai-agents-deep-dive.md)：主精读，聚焦本篇独有命题。
2. [`01-concept-grader-taxonomy.md`](./01-concept-grader-taxonomy.md)：评分器三分法：代码 / 模型 / 人类
3. [`02-concept-capability-and-regression-lifecycle.md`](./02-concept-capability-and-regression-lifecycle.md)：能力评测与回归评测生命周期
4. [`03-concept-swiss-cheese-evaluation-stack.md`](./03-concept-swiss-cheese-evaluation-stack.md)：瑞士奶酪式多层评估防线

## 跨文直接引用（去重）
以下内容在其他目录已有完整展开，本目录只保留必要连接，不重复铺陈：
- [Building effective agents](../building-effective-agents/00-building-effective-agents-deep-dive.md)（概念索引：[`01-concept-workflow-vs-agent-boundary.md`](../building-effective-agents/01-concept-workflow-vs-agent-boundary.md)）
- [How we built our multi-agent research system](../multi-agent-research-system/00-multi-agent-research-system-deep-dive.md)（概念索引：[`01-concept-lead-subagent-architecture.md`](../multi-agent-research-system/01-concept-lead-subagent-architecture.md)）
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)（概念索引：[`01-concept-overlapping-incident-diagnosis.md`](../a-postmortem-of-three-recent-issues/01-concept-overlapping-incident-diagnosis.md)）

## 目录结构说明
- 主文：`00-demystifying-evals-for-ai-agents-deep-dive.md`
- 概念专题：3 篇，按“关键概念是否需要独立建模”自适应拆分。
- 引用规范：关键结论引用原文；跨文共通知识直接引用对应目录。
