# Building Agent Study

一个面向 **Agent 工程学习与实践** 的中文深度学习项目。

这个仓库围绕 Anthropic / Claude 相关的 15 篇核心文章（含官方工程博客与最佳实践文档），做了系统化精读与结构化沉淀：
- 从“Agent 是什么、何时该用”开始；
- 逐步进入工具设计、上下文工程、长任务编排、多代理系统；
- 最终落到评测体系、安全沙箱、工程复盘与生产可靠性。

如果你希望不是“看几篇文章涨见识”，而是能真正建立 **可落地、可验证、可迭代** 的 Agent 工程方法，这个项目就是为你准备的。

## 这个项目的价值

- **理论由浅入深**：从方法论地基到生产级治理，学习曲线连续。
- **不是翻译，而是精读**：每篇都有核心命题、机制拆解、反模式、创新推演。
- **强调可迁移性**：每篇都配实践清单（Checklist），可直接用于项目评审与迭代。
- **跨文去重引用**：共通知识只在主责文章完整展开，其他目录直接引用，避免重复阅读成本。
- **工程视角优先**：关注可观测、可回滚、可评测、可持续，而非“提示词玄学”。

## 学习路线（推荐）

### 第一阶段：方法论地基（先建立正确框架）
1. [building-effective-agents](./building-effective-agents)
2. [writing-effective-tools-for-agents](./writing-effective-tools-for-agents)
3. [effective-context-engineering-for-ai-agents](./effective-context-engineering-for-ai-agents)
4. [introducing-contextual-retrieval](./introducing-contextual-retrieval)
5. [introducing-advanced-tool-use](./introducing-advanced-tool-use)
6. [the-think-tool](./the-think-tool)
7. [equipping-agents-for-the-real-world-with-agent-skills](./equipping-agents-for-the-real-world-with-agent-skills)

### 第二阶段：系统化工程与生产治理（把能力落地）
1. [effective-harnesses-for-long-running-agents](./effective-harnesses-for-long-running-agents)
2. [multi-agent-research-system](./multi-agent-research-system)
3. [code-execution-with-mcp](./code-execution-with-mcp)
4. [demystifying-evals-for-ai-agents](./demystifying-evals-for-ai-agents)
5. [beyond-permission-prompts-claude-code-sandboxing](./beyond-permission-prompts-claude-code-sandboxing)
6. [claude-code-best-practices-for-agentic-coding](./claude-code-best-practices-for-agentic-coding)
7. [a-postmortem-of-three-recent-issues](./a-postmortem-of-three-recent-issues)

### 已有完整精读（历史基线）
- [Building-agents-with-the-Claude-Agent-SDK](./Building-agents-with-the-Claude-Agent-SDK)

## 仓库结构

每篇文章目录默认包含：
- `README.md`：导读、阅读顺序、跨文引用入口
- `00-<slug>-deep-dive.md`：主精读（核心命题 / 机制 / 工程映射 / 反模式 / 创新）
- `01/02/03-concept-*.md`：关键概念专题（边界 / 局限 / 替代方案 / 理论推演）

根目录文件：
- [A社博客精读.md](./A社博客精读.md)：总清单与状态
- `README.md`（当前文件）：项目总导航与学习路径

## 如何高效使用这个仓库

- 先按推荐顺序读主文（`00-*`），再按需深入概念专题。
- 每读完一篇，用文末 Checklist 对你手头 Agent 项目做一次自检。
- 建议建立自己的“失败样例库”：把线上问题映射到对应章节与概念专题。
- 不要追求一次读完，建议按“方法论 -> 工具 -> 评测 -> 安全”四周节奏推进。

## 适合谁

- 想从 0 到 1 系统学习 Agent 工程的开发者
- 已经在做 Agent，但遇到稳定性、成本、评测和安全问题的团队
- 需要搭建内部 Agent 研发方法论与知识库的技术负责人

## License

当前仓库为学习研究用途。如需开源发布，建议补充明确的 LICENSE 文件（如 MIT）。
