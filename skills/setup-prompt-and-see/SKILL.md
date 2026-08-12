---
name: setup-prompt-and-see
description: 選填設定：場景資料夾、場景語言、下游規格格式。沒跑也能用——各 skill 有預設值。
disable-model-invocation: true
---

# setup-prompt-and-see — 選填設定

**不是必經步驟**：缺少 config 時各 skill 用預設值，真正需要時再問。能從 repo 自己查到的資訊（專案用什麼語言）不問使用者。MVP 固定住 `behaviors/mvp/`、入口固定是 `index.html`——不是設定項。

用 `interviewing` 的問法，一輪問完（每題附推薦答案）：

1. **場景資料夾**：預設 `behaviors/`。既有專案已有慣例（如 `.spec/`）就沿用。
2. **場景語言**：預設 `zh-TW` 中文 Gherkin；也可 `en`。
3. **下游規格格式**：SpecKit／OpenSpec／自家格式／不需要，`/to-spec` 會照這裡的設定。

答案依 [CONFIG-FORMAT.md](./CONFIG-FORMAT.md) 的樣板寫入 `behaviors/config.md`——三個標題一律齊全，沒設定的寫「未設定」。

完成後展示主流程一句話：**`/map-it` 盤行為 → `/to-mvp` 做成可操作的靜態 MVP → 想改就繼續下指令 → 交接時 `/to-handoff`。**
