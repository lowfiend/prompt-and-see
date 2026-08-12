# behaviors/config.md 格式

`/setup-prompt-and-see` 輸出的固定樣板。**七個標題一律齊全**——沒設定的寫「未設定」，不准省略標題；下游 skill 按標題讀取，格式穩定它們才好讀。

## 設定檔的位置（固定，不可配置）

設定檔**永遠住在 `behaviors/config.md`**；「場景資料夾」欄位可以指向其他位置（如 `.spec/`），但設定檔本身不搬家。沒有這個檔＝未 setup：各 skill 用預設值（場景根目錄＝`behaviors/`）。各 skill 本體都印有一句話版本，不依賴本檔被讀到。

```markdown
# prompt-and-see 設定

> 由 /setup-prompt-and-see 生成與更新。手改可以，標題結構勿動。

## 場景資料夾
behaviors/

## 場景語言
zh-TW

## 設計系統文件
DESIGN.md（repo 根目錄）

## 殼層來源
未設定
<!-- 可選：宿主 build 萃取（附 build 產物路徑——編譯後 CSS、字型檔所在）。設了它，/to-mvp 從 build 產物萃取殼層——樣式保真，元件行為仍由場景生成；留「未設定」則退回 UI 設計 skill → 設計系統文件 → 中性樣式 -->

## 下游規格格式
未設定
<!-- 可選：SpecKit spec.md／OpenSpec proposal／自家格式（附既有檔案路徑） -->

## UI 設計 skill
未設定
<!-- 填團隊慣用的 UI 設計 skill 名稱，/to-mvp 會明確呼叫它；留「未設定」則退回設計系統文件或中性樣式 -->

## 交付模型
整合原型
<!-- 預設「整合原型」（脈絡＋標註，給 behaviors/ 路徑）。真有把單一功能打包給外部的情境才改「可攜單包」，/to-handoff 據此決定傳遞方式 -->
```

## 誰讀哪一格

| 標題 | 讀取者 |
|---|---|
| 場景資料夾 | **所有 skills**（各 skill 文件以預設 `behaviors/` 行文，實際路徑以此格為準） |
| 場景語言 | `map-it`、`remap`、`behavior-mapping` |
| 設計系統文件、殼層來源、UI 設計 skill | `to-mvp` |
| 下游規格格式 | `to-spec` |
| 交付模型 | `to-handoff` |
