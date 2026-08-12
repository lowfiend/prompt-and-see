# Changelog

## 0.2.0 — 2026-08-12

`to-mvp` 哲學轉向：可攜自足島 → 整合原型（脈絡＋標註）。

- `behaviors/mvp/`（新保留字，`map-it` 開 slug 時擋）＝整合原型：一畫面一頁面檔，每頁合併所有已凍結需求的行為（含失敗態）；共享 `assets/` 殼層（來源優先序：宿主 build 萃取——只承諾樣式保真＞UI 設計 skill＞設計系統文件＞中性；字型 self-host、禁 CDN）；入口頁 `behaviors/mvp/index.html` 由 `/to-mvp` 生成
- 廢除 `behaviors/<slug>/mvp/` 與單檔自足鐵律；`/to-mvp` 改為**全量重生**：每次讀取全部已凍結需求、重生整個原型——自然清掉改名頁、孤兒頁與手改；先在臨時目錄生成並驗證（節點覆蓋、失敗態可觸發、連結不斷），成功才替換、失敗保留舊原型；跨需求矛盾即停；檔名由畫面名稱轉 kebab-case、碰撞即停
- 每個已凍結需求落檔 `coverage.md`（地圖節點 × 頁面／狀態的人可讀表格；整檔覆蓋的當前快照、不累積歷史；檔頭逐檔記 `.feature` 的 SHA-256）；文案兩級：場景釘死照抄、未釘死補中性文案，要穩定就回場景釘死
- `to-handoff`：交付＝整合原型（脈絡）＋覆蓋對照表（標註）；可攜單包＝需求資料夾＋整個 `mvp/`（連結閉包天然成立），保留相對目錄層級；把關：來源 hash 不符或缺頁／無法觸發不准交付，未操作驗證與他需求缺口如實轉錄
- `behavior-mapping`：畫面名稱入 `CONTEXT.md` 詞彙表（頁的身分）；地圖改動＝原型待重生，`mvp/` 一律歸 `/to-mvp` 管；map 檔頭變更紀錄設上限（最近 5 筆，完整歷史交給 Git）、關鍵決定只列現行有效
- config 新增「殼層來源」「交付模型」（五標題 → 七標題）；設定檔固定住 `behaviors/config.md`，「場景資料夾」欄位決定實際根目錄

## 0.1.0 — 2026-08-11

首個版本。範圍：從一句需求到交付包。

- 10 個 skills：使用者呼叫 `setup-prompt-and-see`／`map-it`／`remap`／`to-spec`／`to-mvp`／`to-handoff`；模型呼叫 `interviewing`／`scenario-writing`／`behavior-mapping`／`domain-language`
- `behaviors/` 結構：純 slug 需求資料夾＝功能身分證；場景檔唯一手寫，其餘單向生成；`index.html` 總覽（按功能＋按畫面反查）
