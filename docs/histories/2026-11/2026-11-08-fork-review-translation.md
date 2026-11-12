## 2026-11-08 | 任务：恢复 fork PR 行内评论翻译

**Links:** [执行计划](../../exec-plans/completed/2026-11/2026-11-08-fork-review-translation.md)

### 执行上下文

- **Agent Name:** `Codex`
- **Model ID:** `GPT-6`
- **Environment:** `macOS 27.0.1 / Xcode 27.2 (27B52)`

### 用户请求

用两段 workflow 恢复 fork PR 的行内评论翻译，并在本地验证。

### 变更

- 新增 `REVIEW_COMMENT_ID` 和 `REVIEW_PULL_NUMBER`，读取并核对 GitHub 原评论。
- 回复原线程，按源评论 ID 跳过已发布的译文，更新文档、测试和运行包。

### 设计意图

显式入口让有写权限的工作流复用相同翻译逻辑。线程回复使用顶层评论 ID。

### 验证

- `npm run format-check`、`npm test -- --runInBand`（62 项）、`npm run build`、`npm run lint` 和 `npm run package` 通过。
- Action YAML、Node 24 入口及打包差异检查通过。
- 未触发真实 workflow 或发布 GitHub 评论。

### 受影响文件

- `src/main.ts`、`action.yml`、`dist/`、`__tests__/main.test.ts`、相关 README 和专题文档。

### 后续事项

- 后续需将本地 Action 提交发布到 GitHub，Easydict 的固定引用才能解析。
