# x-trending.json schema（情报官中文热帖）

页面 `public/x.html` 兼容两种顶层形状：

1. `{ "updatedAt": "...", "items": [ ... ] }`（推荐，幕僚长写入 data/public 时用）
2. 裸数组 `[ ... ]`（情报官实验文件）

## item 字段

| 字段 | 必填 | 说明 |
|------|------|------|
| title | 是 | 标题 |
| authorName | 推荐 | 显示名（卡片顶部） |
| authorHandle | 推荐 | `@handle` |
| summary | 推荐 | 摘要 |
| url | 是 | 必须是 `https://x.com/{handle}/status/{id}` |
| metrics.likes / reposts / views / replies | 有则显示 | 互动数 |
| relativeTime | 可选 | 如 `4h`，优先显示在作者行 |
| fetchedAt | 推荐 | ISO8601 |
| why / status / accounts / author | 可选 | 兼容旧字段；作者也可写 `author: {name, handle}` |

## 规则
- url 必须是具体 status 帖，不要话题搜索页。
- 首页「X (Twitter)」话题词栏是另一条链路，不要混进本 JSON。
