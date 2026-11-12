# 升级 tisfeng/skills 至 v0.7.0

- 状态：completed
- 创建日期：2026-09-27
- 负责人：Codex
- 关联 Issue/PR：https://github.com/tisfeng/skills/releases/tag/v0.7.0

## 执行上下文

- **Agent Name:** Codex
- **Model:** GPT-5
- **Environment:** macOS 27.0 / Xcode 27.2 (27B5019j)

## 背景

issues-translate-action 当前固定使用 tisfeng/skills v0.6.2，上游已发布 v0.7.0，需要同步六个外部受管 Skill。

## 目标与范围

- 目标结果：六个受管 Skill、lock、来源参考和第三方通知固定到 v0.7.0。
- 允许修改路径：六个 .agents/skills/ 受管目录、skills-lock.json、docs/references/tisfeng-skills.md、THIRD_PARTY_NOTICES.md、本任务 plan/history。
- 同任务 history：docs/histories/2026-09/2026-09-27-upgrade-tisfeng-skills-v0.7.0.md
- 用户限制：不修改 SelectedTextKit；不添加测试；不 push、不创建 PR、不发布、不触发真实 workflow。
- 非目标：不修改项目专属 release Skill、Action runtime、测试、依赖、workflow 或其他第三方来源。
- 验收标准：六个目录与 v0.7.0 一致，lock、来源参考和第三方通知同步，项目专属路径保持不变，并创建独立本地提交。

## 工作计划

1. 用固定安装器从 v0.7.0 tag 同步六个完整 Skill 目录。
2. 更新来源参考、第三方通知和 plan/history，保护项目专属路径。
3. 完成受管快照、JSON、Markdown、保护路径和 git diff --check 检查后创建本地提交。

## 风险与决策

- 使用已发布 tag，不使用 main 或未发布提交。
- 安装器只选择 tisfeng/skills 的六个 Skill，不覆盖项目专属 release Skill 或 Action 运行时。

## 进度

- [x] 同步受管目录和 lock。
- [x] 更新来源、验证并审查完整任务差异。
- [x] 写入 history、归档 plan 并创建本地提交。

## 验证

- 记录六个受管目录逐文件匹配 v0.7.0 tag tree、目录 hash 与 lock 一致性。
- 记录 JSON、Markdown、保护路径和 git diff --check 结果；不运行真实 workflow。
- 六个受管目录逐文件匹配上游 tag；目录 hash 与 lock 全部一致。JSON、Python compileall、Shell 语法、frontmatter、保护路径和 git diff --check 通过；未运行真实 workflow。
- review 复查最终差异未发现有效 finding；未修改 Action runtime、依赖、测试或 workflow。

## 完成条件

- [x] 六个受管目录、lock、来源参考和第三方通知统一到 v0.7.0。
- [x] 必要验证通过，项目专属 Skill 与 Action runtime 未被修改。
- [x] plan 归档，history 与依赖更新一起提交。
