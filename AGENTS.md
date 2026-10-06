# billflare-reports - 公开 Cloudflare 账单报告的 GitHub 收集入口
GitHub Issue Forms + YAML + Markdown

<directory>
.github/ - issue chooser 与中英报告表单
</directory>
<config>
AGENTS.md - 项目规则、证据边界与验收要求。
CLAUDE.md - 指向 AGENTS.md 的相对软链。
README.md - 中英投稿入口、公开范围与隐私提醒
</config>

## Purpose

- 只收集公开 Cloudflare 账单报告。
- 每份提交都会成为公开 GitHub Issue。
- `pending-review` 表示等待来源审阅。
- Issue 不代表事实已核验。
- Issue 不代表已收录到 Billflare。

## Submission Boundary

- 表单收集公开 HTTPS 来源、可选报告别名、产品、可选金额、后续来源和事实摘要。
- 表单必须要求公开同意。
- 别名由报告人填写，不验证身份。
- 不收集账号、邮件、私信、账单凭据或私人账单。
- 不提供文件上传字段。
- 所有用户输入都视为公开文本。

## Stable Rules

- 保持中文与英文表单字段一一对应。
- 保持 `report-zh.yml` 与 `report-en.yml` 文件名稳定。
- 网站通过 `template` 参数直达对应语言表单。
- 两个表单都保留 `pending-review` 标签。
- 禁止提交空白 Issue。
- 禁止把模板描述成自动核验或自动收录。
- 只写稳定规则，不记录任务进度或验收流水账。

## Verification

- 用 Ruby Psych 解析所有 YAML。
- 检查表单字段 ID 不重复。
- 检查来源、产品、摘要和公开同意必填。
- 检查两个表单都有 `pending-review` 标签。
- 用 `gh api` 读取默认分支文件；不创建测试 Issue。

法则：先说明公开范围，再收集最少信息。

[PROTOCOL]: 变更时更新此头部，然后检查 CLAUDE.md
