---
name: setup-prompt-and-see
description: 在一個 repo 裡第一次使用這套 skills 前的設定。每個 repo 跑一次。
disable-model-invocation: true
---

# setup-prompt-and-see — 每個 repo 跑一次

用 `interviewing` 的問法，一輪問完以下設定（每題附推薦答案）：

1. **場景資料夾放哪**：預設 `behaviors/`。既有專案已有慣例（如 `.spec/`）就問要並存還是遷移。
2. **場景語言**：預設 `zh-TW` 中文 Gherkin；也可 `en`。
3. **設計系統文件**：有沒有 `DESIGN.md` 或同等文件？`/to-mvp` 會對齊它。
4. **下游規格格式**：SpecKit／OpenSpec／自家格式／不需要。`/to-spec` 會照這裡的設定。
5. **慣用的 UI 設計 skill**（選填）：如果團隊有偏好的視覺設計 skill，寫下名稱；`/to-mvp` 生成畫面時會明確呼叫它，而不是碰運氣等它自動觸發。先確認該 skill 確實已安裝（列出目前可用的 skills 給使用者對照），沒裝就提醒安裝方式再寫入。

答案依 [CONFIG-FORMAT.md](./CONFIG-FORMAT.md) 的樣板寫入 `behaviors/config.md`——五個標題一律齊全，沒設定的寫「未設定」。其他 skills 執行時先讀這份設定；沒有設定檔就用各自的預設值並提醒可跑本 skill。

設定完成後，向使用者展示主流程一句話：**`/map-it` 盤行為 → 凍結 → `/to-mvp` 看畫面 → `/to-handoff` 交出去；要改就 `/remap`。**
