# Loon-Rules

个人自持维护的 Loon 分流规则集（`.lsr` 格式），针对主流 AI 服务补充完善官方最新域名、沙箱 iframe 与 CDN 端点，避免因规则遗漏落入兜底节点。

## 规则清单

| 规则文件 | 说明 | 订阅直链（Raw） |
|---|---|---|
| `OpenAI.lsr` | OpenAI / ChatGPT / Sora / 静态资源 CDN 规则 | `https://raw.githubusercontent.com/Badakonpro/Loon-Rules/main/OpenAI.lsr` |
| `Claude.lsr` | Anthropic Claude / 官方 Web / 沙箱与协议端点 | `https://raw.githubusercontent.com/Badakonpro/Loon-Rules/main/Claude.lsr` |
| `Gemini.lsr` | Google Gemini / DeepMind / Code Assist | `https://raw.githubusercontent.com/Badakonpro/Loon-Rules/main/Gemini.lsr` |

## Loon 引用格式示例

在 `[Remote Rule]` 中添加：

```ini
# AI 服务自持分流规则
https://raw.githubusercontent.com/Badakonpro/Loon-Rules/main/OpenAI.lsr, policy=AI, tag=OpenAI, enabled=true
https://raw.githubusercontent.com/Badakonpro/Loon-Rules/main/Claude.lsr, policy=AI, tag=Claude, enabled=true
https://raw.githubusercontent.com/Badakonpro/Loon-Rules/main/Gemini.lsr, policy=AI, tag=Gemini, enabled=true
```

## 2026-11-02 核对更新

固定上游 `v2fly/domain-list-community` 提交
`01add61fbaf719b55673d969615cd328e80f214c`（2026-11-01），仅合入经用途核对的最小增补：

- OpenAI：43 → 44 条，增加 `openai.org` 显式规则；原有关键词规则已覆盖，实际范围不变。
- Claude：11 → 15 条，增加 `claude.app`、`claude.dev` 后缀与 `claude.new`、`claudeacademy.com` 精确根域。
- Gemini：43 → 49 条，增加 Gemini Web、Workspace Gemini 与 NotebookLM 的 6 个精确 API 主机。
- 原有规则不删改；不照搬未知正则、不扩大共享 CDN 或 `googleapis.com` 整站；6 个未明确生产用途的 Claude 域名暂缓。
- 本段记录本地维护内容，发布状态以远端仓库为准；未进行 Loon 客户端业务实测。
