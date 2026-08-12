---
name: to-handoff
description: 生成簡短的交接導讀 handoff.md：場景與地圖路徑、MVP 入口與操作方式、本次涉及的檔案、已知事項。使用者呼叫就生成，不設閘門。
disable-model-invocation: true
---

# to-handoff — 交接導讀

使用者呼叫就依**目前狀態**生成 `behaviors/<slug>/handoff.md`，不設任何閘門。它是**導讀**，不是內容複本——場景、地圖、MVP 都在 repo 裡活著，內嵌快照只會與它們漂移。

> 設定住 `behaviors/config.md`（「場景資料夾」決定場景根目錄）；沒有設定檔就用預設值。MVP 固定住 `behaviors/mvp/`、入口固定是 `behaviors/mvp/index.html`——直接引用，不搜尋、不推測、不記錄額外狀態。

## 內容（保持短）

1. 本次需求的 `.feature` 與 `map.md` 路徑。
2. MVP：`behaviors/mvp/`，入口：`behaviors/mvp/index.html`（直接打開就能操作，免安裝免編譯）。
3. 本次涉及的 HTML／CSS／JS 檔案。
4. 如何操作主要情境與失敗／空狀態。
5. **已知事項**：尚未完成、尚未驗證的部分誠實列出——不阻擋交付，讓下游知情。
6. 有下游 spec 就指向 `behaviors/<slug>/spec/`。

## 角色提示（一句話級）

- **QA**：場景即測項；發現場景漏了行為，回報回場景檔，不得只補在測試裡。
- **RD**：照場景與 MVP 施工；場景沒有的行為先回 `/map-it` 討論，不自行發明。
- **UIUX**：MVP 是行為載體；涉及行為的意見回場景檔討論。

## 硬規則

- 不複製場景全文與地圖、不寫版本歷史、不建立 manifest 或打包協定；歷史、版本、diff 交給 Git。
- 單向生成：只讀場景／地圖／MVP，絕不反向修改它們。
