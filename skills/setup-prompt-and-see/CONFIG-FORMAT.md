# behaviors/config.md 格式

`/setup-prompt-and-see` 輸出的固定樣板。**五個標題一律齊全**——沒設定的寫「未設定」，不准省略標題；下游 skill 按標題讀取，格式穩定它們才好讀。

```markdown
# prompt-and-see 設定

> 由 /setup-prompt-and-see 生成與更新。手改可以，標題結構勿動。

## 場景資料夾
behaviors/

## 場景語言
zh-TW

## 設計系統文件
DESIGN.md（repo 根目錄）

## 下游規格格式
未設定
<!-- 可選：SpecKit spec.md／OpenSpec proposal／自家格式（附既有檔案路徑） -->

## UI 設計 skill
未設定
<!-- 填團隊慣用的 UI 設計 skill 名稱，/to-mvp 會明確呼叫它；留「未設定」則退回設計系統文件或中性樣式 -->
```

## 誰讀哪一格

| 標題 | 讀取者 |
|---|---|
| 場景資料夾、場景語言 | `map-it`、`remap`、`behavior-mapping` |
| 設計系統文件、UI 設計 skill | `to-mvp` |
| 下游規格格式 | `to-spec` |
