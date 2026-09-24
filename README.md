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
