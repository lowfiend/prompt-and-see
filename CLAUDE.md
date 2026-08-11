# CLAUDE.md

本 repo 是純 Markdown 的 agent skills 集合（無程式碼、無建置）。修改時遵守：

1. **主持人不呼叫主持人**：使用者呼叫的 skill（`disable-model-invocation: true`）可引用模型零件（interviewing、scenario-writing、behavior-mapping、domain-language），不可引用另一個使用者呼叫的 skill。
2. **通用 skill 只放佔位符**：SKILL.md 的範本區塊用 `<佔位符>`；具體內容只能以「例」的身分出現在說明文字，明確標注，且**例子必須產業中性**（用電商訂單這類普世情境，不准出現任何特定產業、公司、產品的字樣）。格式檔的活範例一律指向本 repo 自己的檔案（吃自己的藥）。
3. **改 skill 要同步**：README 的 skills 表格與所有內文交叉引用一起改，grep 確認零殘留。
4. **憲法四條**見 README「硬規則」——任何修改不得違反；用詞遵守根目錄 `CONTEXT.md`。
