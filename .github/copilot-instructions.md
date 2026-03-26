# AI-SDD Framework — 專案指引

本專案使用 **AI-SDD（Specification-Driven Development）** 流程進行開發。所有程式碼變更必須遵循以下原則。

## 核心流程

1. **規格先行**：所有功能必須先撰寫規格文件（`docs/sdd/specs/`），經確認後才開始實作
2. **設計導向**：複雜功能需先完成系統設計（`docs/sdd/designs/`）和架構決策記錄（`docs/sdd/decisions/`）
3. **可追蹤**：每個 commit 和 PR 須引用對應的規格文件編號
4. **測試驗證**：實作完成後須撰寫測試，驗證是否符合規格中定義的驗收條件

## 開發流程概覽

```
需求 → 規格 → 設計 → 實作 → 測試 → 審查 → 迭代
```

每個階段有對應的 Prompt（`/01-init-project` 至 `/07-iterate`）和專屬 Agent（`@sdd-pm`, `@sdd-architect`, `@sdd-developer`, `@sdd-reviewer`）。

## 程式碼品質要求

- 遵循專案既有的程式碼風格和架構模式
- 新增程式碼必須有對應的測試
- 不引入已知的安全漏洞（參照 OWASP Top 10）
- 保持函式單一職責，模組低耦合
- 命名清晰具描述性，減少不必要的註解

## SDD 文件結構

- `docs/sdd/specs/` — 功能規格書
- `docs/sdd/designs/` — 系統設計文件
- `docs/sdd/decisions/` — 架構決策記錄（ADR）
- `docs/sdd/test-plans/` — 測試計劃
- `sdd/templates/` — 文件範本

## 重要規則

- 實作前必須確認規格文件存在且已審查
- 不做規格外的「順便改善」— 額外變更需要額外的規格
- 每個 PR 只處理一個規格項目
- 遇到規格不明確的部分，先更新規格再實作
