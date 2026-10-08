# MCP 写入链路验证（可删除）

| 项 | 值 |
| --- | --- |
| 时间 | 2026-10-08 |
| 发起端 | DeepSeek Harness 桌面版 0.2.0-rc.2 |
| 通道 | `@hyzyn/dsh-mcp` 插件 → GitHub MCP Server（`https://api.githubcopilot.com/mcp/`） → GitHub Contents API |
| 调用 | `create_or_update_file`（新建文件，附 commit） |
| 结果 | 成功 —— 本文件即产物 |

## 这条链路解决了什么

- **不需要本地 git**：不是 `git push`，而是 REST API 直接提交，因此不受本机 ssh/git 证书栈故障影响。
- **不需要网页拖拽**：过去向仓库传文件靠 GitHub 网页的 “upload files”，现在可以由 agent 完成。
- **能力范围**：新建/更新/删除单个文件、一次提交多个文件、建分支、发 PR、建 issue 等。

## 验证方法（复核用）

1. 本文件应出现在 `TJ1024yjy/tjsys` 的 `main` 分支根目录；
2. 该 commit 的作者应为账号 `TJ1024yjy`（使用其 OAuth 凭据提交）；
3. 内容与预期一致即证明写入链路完整可用。

> 本文件仅为链路验证产物，**可随时删除**。
