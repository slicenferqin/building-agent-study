# 03. 概念专题：Skill 供应链安全与治理

> 所属主文：[`00-equipping-agents-for-the-real-world-with-agent-skills-deep-dive.md`](./00-equipping-agents-for-the-real-world-with-agent-skills-deep-dive.md)
>
> 原始来源：[Equipping agents for the real world with Agent Skills](https://claude.com/blog/equipping-agents-for-the-real-world-with-agent-skills)

## 一、概念定义与语义边界
将 skill 视作可执行依赖，按软件供应链思路进行来源、内容与行为审计。

## 二、原文为何选择该概念（问题-方案匹配）
原文明确提醒恶意 skill 可能诱导数据外泄或执行危险动作。

## 三、局限性与失效条件（反例）
1. 人工审计成本高，不易规模化。
2. 动态下载资源会绕过静态检查。
3. 信任边界跨组织时责任划分复杂。

## 四、替代路线（至少两条）与 trade-off
- **完全信任社区技能**：扩展快但风险高。
- **严格私有仓策略**：安全强但创新外溢不足。

## 五、理论推演与创新
可引入“技能 SBOM（软件物料清单）+ 行为策略测试”作为上线门槛。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Claude Code sandboxing》中的边界隔离机制应协同设计。
- 直接引用目录：
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)
- [Writing effective tools for agents — with agents](../writing-effective-tools-for-agents/00-writing-effective-tools-for-agents-deep-dive.md)
- [Beyond permission prompts: making Claude Code more secure and autonomous](../beyond-permission-prompts-claude-code-sandboxing/00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)

## 七、实战检查清单
- 我是否给“Skill 供应链安全与治理”定义了可观测指标？
- 我是否为“人工审计成本高，不易规模化。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Equipping agents for the real world with Agent Skills](https://claude.com/blog/equipping-agents-for-the-real-world-with-agent-skills)
- 外部理论锚点：软件供应链安全；零信任架构
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
