---
name: to-spec
description: 把當前 BDD 場景忠實轉成下游規格格式——SpecKit、OpenSpec 或團隊自家格式。要把行為描述交給規格流程時使用。
disable-model-invocation: true
---

# to-spec — 場景 → 下游規格

BDD 場景是行為的原始碼；下游團隊要什麼規格格式，就替他們生成什麼。本 skill 是**轉接頭**：不擁有流程、不發明格式，只做忠實轉換。使用者呼叫就依當前場景生成，沒有前置條件。

> 設定住 `behaviors/config.md`（「場景資料夾」欄位決定實際根目錄）；沒有設定檔就用預設值。

## 目標格式

先看 config「下游規格格式」；沒有就問使用者——(A) SpecKit `spec.md`、(B) OpenSpec change proposal、(C) 團隊自家格式——以你們 repo 裡既有的規格檔為準，讀它的結構照樣生成。

## 產出位置

寫入 `behaviors/<slug>/spec/`——檔名依目標格式（SpecKit → `spec.md`；OpenSpec → `proposal.md`；自家格式照既有慣例命名）。`spec/` 整夾是生成文件，可整包刪掉重生。

## 轉換規則

1. **行為部分照搬，不改寫**：user story、驗收標準直接引用場景內容。不准只挑「重點場景」。
2. **技術部分明示缺口**：架構、API 形狀、資料庫、拆工不在場景裡——用明確的 TODO 區塊標「此節需技術訪談補齊」，**不准腦補技術決策**。
3. **檔頭一行**：「本檔由 `behaviors/<slug>/` 生成——行為要改請改場景檔後重生。」

## 硬規則

- 單向生成：絕不從規格文件反向改場景。
- 一次一個目標格式；要餵多個下游就跑多次，各自生成。
