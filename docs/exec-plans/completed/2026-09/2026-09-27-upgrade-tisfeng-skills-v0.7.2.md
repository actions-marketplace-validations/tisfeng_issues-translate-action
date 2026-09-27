# 升级 tisfeng/skills 至 v0.7.2

- 状态：active
- 创建日期：2026-09-27
- 负责人：Codex
- 关联 Issue/PR：https://github.com/tisfeng/skills/releases/tag/v0.7.2

## 执行上下文

- **Agent Name:** `Codex`
- **Model:** `GPT-5`
- **Environment:** `macOS 27.0 / Xcode 27.2 (27B5019j)`

## 背景

issues-translate-action 当前固定使用 tisfeng/skills v0.7.0，上游将发布 v0.7.2，需要同步六个外部受管 Skill。

## 目标与范围

- 目标结果：六个受管 Skill、lock、来源参考和第三方通知固定到 v0.7.2。
- 允许修改路径：六个 `.agents/skills/` 受管目录、`skills-lock.json`、`docs/references/tisfeng-skills.md`、`THIRD_PARTY_NOTICES.md`、本任务 plan/history。
- 同任务 history：`docs/histories/2026-09/2026-09-27-upgrade-tisfeng-skills-v0.7.2.md`
- 用户限制：不修改 Raycast-Easydict、SelectedTextKit、Action 产品代码或 workflow。
- 非目标：不修改项目专属 `release` Skill、依赖、测试或打包产物。
- 验收标准：六个目录与 v0.7.2 一致，lock、来源和第三方通知同步，并创建本地提交。

## 工作计划

1. 从固定 v0.7.2 tag 安装六个完整 Skill 目录。
2. 更新来源参考、第三方通知、plan/history 并核对项目专属 Skill。
3. 运行静态检查、受管 Skill 测试和快照校验，创建本地提交。

## 风险与决策

- 仅同步 tisfeng/skills 的六个 lock-governed Skill，不覆盖项目专属 release Skill。
- 不手工修改 lock hash，使用安装器生成并独立重算确认。

## 进度

- [x] 同步受管目录和 lock。
- [x] 更新来源、通知、验证并审查差异。
- [x] 写入 history、归档 plan 并创建本地提交。

## 验证

- 六个受管目录逐文件匹配上游 v0.7.2 tag；使用安装器同一 Node `localeCompare` 排序算法重算目录 hash，六个 hash 均与 lock 一致。
- 运行 `git-commit`、`review`、`review-pr`、`submit-pr`、`worktree-rebase-merge` 的现有测试，共 119 个测试通过；运行 JSON、Shell、frontmatter、保护路径和 `git diff --check` 检查。
- 最终差异 review 未发现有效 finding；未运行真实 GitHub Action workflow，因为本次只同步依赖快照和治理文档。

## 完成条件

- 六个目录、lock、来源参考和第三方通知统一到 v0.7.2。
- 项目专属 Skill、Action 代码、依赖、测试和 workflow 未被修改。
- plan 归档，history 与依赖更新一起提交。
