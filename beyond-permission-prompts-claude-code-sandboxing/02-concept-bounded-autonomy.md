# 02. 概念专题：有界自治（Bounded Autonomy）

> 所属主文：[`00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md`](./00-beyond-permission-prompts-claude-code-sandboxing-deep-dive.md)
>
> 原始来源：[Beyond permission prompts: making Claude Code more secure and autonomous](https://www.anthropic.com/engineering/claude-code-sandboxing)

## 一、概念定义与语义边界
让 agent 在预定义安全边界内高自治运行，而不是全局无限放权。

## 二、原文为何选择该概念（问题-方案匹配）
目标不是“更少确认”本身，而是在可控风险内释放自动化价值。

## 三、局限性与失效条件（反例）
1. 边界定义不清会造成误阻或误放。
2. 用户对边界语义理解不足会降低信任。
3. 跨项目复用边界策略难度高。

## 四、替代路线（至少两条）与 trade-off
- **全手动审批**：安全可感知但效率低。
- **全跳过审批**：效率高但风险不可接受。

## 五、理论推演与创新
建议建立“自治信用分”：根据历史行为动态调整可自动执行范围。

## 六、与其他博客概念关联（去重引用）
- 本文只展开本概念在当前语境下的边界与创新，不重复复述通用背景。
- 关联说明：与《Long-running harnesses》的长期会话治理可结合为持续自治框架。
- 直接引用目录：
- [Claude Code: Best practices for agentic coding](../claude-code-best-practices-for-agentic-coding/00-claude-code-best-practices-for-agentic-coding-deep-dive.md)
- [Code execution with MCP: Building more efficient agents](../code-execution-with-mcp/00-code-execution-with-mcp-deep-dive.md)
- [A postmortem of three recent issues](../a-postmortem-of-three-recent-issues/00-a-postmortem-of-three-recent-issues-deep-dive.md)

## 七、实战检查清单
- 我是否给“有界自治（Bounded Autonomy）”定义了可观测指标？
- 我是否为“边界定义不清会造成误阻或误放。”准备了降级策略？
- 我是否对两条替代路线做过任务级对照，而非主观判断？
- 我是否在评测中纳入了该概念最常见的失败场景？

## 八、来源与外部理论
- 主来源：[Beyond permission prompts: making Claude Code more secure and autonomous](https://www.anthropic.com/engineering/claude-code-sandboxing)
- 外部理论锚点：可控自治系统；人机协同中的信任校准
- 说明：外部锚点用于拓展迁移能力，不替代主来源结论。
