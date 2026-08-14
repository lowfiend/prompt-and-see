# behaviors/config.md 格式

`/setup-prompt-and-see` 輸出的固定樣板。**兩個標題一律齊全**——沒設定的寫「未設定」，不准省略標題；下游 skill 按標題讀取，格式穩定它們才好讀。

MVP 不是設定項：固定住 `behaviors/mvp/`，入口固定是 `behaviors/mvp/index.html`。

## 設定檔的位置（固定，不可配置）

設定檔**永遠住在 `behaviors/config.md`**；「場景資料夾」欄位可以指向其他位置（如 `.spec/`），但設定檔本身不搬家。沒有這個檔＝未 setup：各 skill 用預設值（場景根目錄＝`behaviors/`）。

```markdown
# prompt-and-see 設定

> 由 /setup-prompt-and-see 生成與更新。手改可以，標題結構勿動。

## 場景資料夾
behaviors/

## 場景語言
zh-TW
```

## 誰讀哪一格

| 標題 | 讀取者 |
|---|---|
| 場景資料夾 | **所有 skills**（各 skill 文件以預設 `behaviors/` 行文，實際路徑以此格為準） |
| 場景語言 | `map-it`、`behavior-mapping` |
