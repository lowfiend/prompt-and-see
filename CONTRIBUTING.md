# 貢獻指南

本 repo 是一個人每天在用的 skills 集合，策展式維護：想法歡迎，每一個都用下面的門檻衡量。

## 門檻

issue 要同時過兩關才會留著：

1. **觀察到的失敗**。描述真實 session 裡發生的事：跑了什麼、skill 做了什麼、你預期什麼，附重現步驟。「如果……會更好」這種假設性改善不算。這和 `reproducing` 零件是同一條紀律：先跑出來，才算問題。
2. **符合哲學**。不是下面「已決定不做」裡的東西，也不是只為某一個人的工作流程做的調整——那些放你自己專案的 `CLAUDE.md`。

大小無關：改一個字與重寫，面對同一道門檻。

## 已決定不做

- **閘門與 hooks**：Stop hook、權限閘、自動檢查屬於 harness（Claude Code 設定、CI），不進 skills repo。
- **產業、公司、產品專屬內容**：skill 通用，例子只准產業中性。
- **個人偏好**：寫進你自己的 `CLAUDE.md`。
- **能由既有 skill 組合出來的新 skill**：不開新的。

## 改 skill 的規矩

以根目錄 `CLAUDE.md` 四條為準，用詞遵守 `CONTEXT.md`。改完驗證：

```bash
claude plugin validate .
claude plugin marketplace add /絕對路徑/prompt-and-see    # 本機路徑當 marketplace
claude plugin install prompt-and-see@prompt-and-see
claude plugin details prompt-and-see@prompt-and-see      # 16 支 skill 都要在
```

## commit 與版本

- Conventional Commits（`feat:`、`fix:`、`docs:`），單行，無 body。
- 一個版本一個 commit；`CHANGELOG.md` 在同一個 commit 內更新。

## Pull request

PR 只開放給協作者。其他人請開 issue 描述問題，修法由維護者設計。

## 用 AI 寫 issue

agent 幫忙可以，但 issue 是你貼的，你負責：

- **一題一 issue**。一次 session 的多個發現是多個 issue，或都不是。
- **一屏內寫完**。放不下就刪。
- **重現步驟先於分析**。
- **不貼整份改寫的 `SKILL.md`、不貼完整提案**。描述問題就好。
- **不是你專案的票**。你的 agent 把自己專案的拆票送來這裡，就是送錯 repo。
