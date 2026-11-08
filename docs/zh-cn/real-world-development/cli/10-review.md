---
title: "第 10 课 - 回顾与后续步骤"
description: "回顾 Copilot CLI 工作流、两个拉取请求、可复用的自定义配置和更多资源。"
authors:
  - geektrainer
lastUpdated: 2026-09-29
---

你在 Tailspin Toys 的连续工作流中使用了 GitHub Copilot CLI。本课中，你：

- 准备了 Codespace，安装 Copilot CLI，探索项目并找到预先创建的筛选议题。
- 添加星级评分，在转发端口的浏览器中检查结果，并手动合并了第一个拉取请求 (PR)。
- 从筛选议题开始，在 Plan 模式下确定方案，在 Autopilot 模式下实现，并在 Interactive 模式下审查。
- 使用自定义指令指导代理，然后自定义现有的 `quality-checks` 技能并用它运行单元测试、lint 和类型检查。
- 添加 Playwright Model Context Protocol (MCP) 服务器，并用它在真实浏览器中探索筛选功能。
- 创建并选择质量保证 (QA) 自定义智能体，以评估需求、覆盖率、技能结果和浏览器证据。
- 审查了完整的筛选更改，并授权 Agent Merge 合并筛选 PR。
- 探索了用于管理上下文、模型、共享和可选云端委派的斜杠命令。

## 交付的内容

本工作坊包含两个 PR 里程碑，分别从更新后的 `main` 创建独立分支：

1. **星级评分：** 在游戏卡片上显示现有的 `starRating` 和明确的未评分状态。
2. **筛选和质量工作流：** 实现筛选，更新指令并将其应用于该功能，自定义 `quality-checks` 报告，创建 QA 配置，并添加相关测试。

从规划筛选功能到创建 PR，你始终使用同一个对话和分支。为简化工作坊，我们将这些工作合并到一个 PR 中。

## 不同的验证方式

你通过多种方式检查代码：自动化测试、亲自在浏览器中检查，以及使用 MCP 让 Copilot 探索浏览器。`quality-checks` 技能运行了单元测试、lint 和类型检查，并按新格式报告结果。QA 在创建 PR 之前，将这些结果与需求和测试覆盖率审查结果汇总在一起。

新增测试应解决实际缺口；QA 运行后不需要添加测试也可能是正确结果。授权合并前，请审查代码和证据；更改后，请更新受影响的证据。

## 最佳实践

提供给 Copilot 的上下文和工具会影响它的工作。在本工作坊中，你更新了指令、自定义了技能、创建了 QA 配置并配置了 MCP 服务器。可以在不同对话中复用这些自定义配置，并根据团队需求调整。指令设定标准，技能描述可重复的任务，自定义智能体定义专门职责，MCP 服务器连接外部工具。请检查实际更改和工具结果，而不只是代理的摘要。

根据任务选择**模式和模型**。在开始构建前思考方案时使用 **Plan**，跟进范围明确的更改时使用 **Interactive**，将范围明确的任务交由代理处理时使用 **Autopilot**。日常编辑选择速度更快的模型，复杂任务选择能力更强的模型。

上下文和基础设施同样重要。清楚说明想构建*什么*、*为什么*构建以及*如何*构建，会显著影响结果。

## 继续探索

你已经完成核心工作流。还可以了解 Copilot CLI 的其他功能：

- 使用 `/review` 请求代码审查智能体分析更改。
- 使用 `/rubber-duck` 讨论问题并获得另一种观点。
- 使用 `/fleet` 并行协调相互独立的子任务。
- 使用 `/worktree` 隔离单独的任务。
- 使用 `/delegate` 将任务发送给 Copilot cloud agent。

## 后续步骤

提升工具使用能力的最好方式就是持续使用它。可以将它用于生产代码、个人项目，或者用于构建那个想了多年却一直没有动手的小应用。与团队分享经验，也向团队学习。一如既往，继续探索文档。

如果想从终端扩展 Tailspin Toys，请继续学习可选的 [Foundry Backer Concierge 系列][foundry]。若要比较其他环境，可以探索 [VS Code 工作坊][vscode]、[GitHub Copilot 应用工作坊][app]或 [Copilot cloud agent 工作坊][cloud]。

## 资源

- [关于 GitHub Copilot CLI][about-cli]
- [Copilot CLI 命令参考][cli-reference]
- [自定义 Copilot CLI][customize-cli]
- [使用 Copilot CLI 管理拉取请求][manage-prs]

[previous-lesson]: ../9-cli-power-tools/
[foundry]: ../8-foundry-agent/
[vscode]: ../../vscode/
[app]: ../../app/
[cloud]: ../../cloud/
[about-cli]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
[customize-cli]: https://docs.github.com/copilot/how-tos/copilot-cli/customize-copilot
[manage-prs]: https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli/manage-pull-requests
