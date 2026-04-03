# AI-SDD Framework

本專案使用 **AI-SDD（Specification-Driven Development）** 流程進行開發。

## 核心流程

所有功能開發遵循 7 階段流程：初始化 → 規格化 → 設計 → 實作 → 測試 → 審查 → 迭代

```
需求 → 規格 → 設計 → 實作 → 測試 → 審查 → 迭代
```

每個階段有對應的 Command（`/01-init-project` 至 `/08-change-request`）和專屬 Agent（`@sdd-pm`, `@sdd-architect`, `@sdd-developer`, `@sdd-reviewer`）。

## 核心規則

1. **規格先行**：實作前必須有規格文件（`docs/sdd/specs/`），經確認後才開始實作
2. **不做規格外的事**：嚴格按規格實作，不擅自添加功能
3. **設計導向**：複雜功能需先完成系統設計（`docs/sdd/designs/`）和架構決策記錄（`docs/sdd/decisions/`）
4. **可追蹤性**：每段程式碼映射到規格中的驗收條件，每個 commit 須引用對應的規格文件編號
5. **測試驗證**：每個驗收條件都有對應的測試

## 文件位置

- 規格書：`docs/sdd/specs/SPEC-{編號}-{名稱}.md`
- 設計文件：`docs/sdd/designs/DESIGN-{編號}-{名稱}.md`
- ADR：`docs/sdd/decisions/ADR-{編號}-{主題}.md`
- 測試計劃：`docs/sdd/test-plans/TEST-{編號}-{名稱}.md`
- 變更請求：`docs/sdd/changes/CR-{編號}-{描述}.md`
- 範本：`sdd/templates/`
- 工作流指南：`sdd/workflows/`

## 工作流指南

CRITICAL: When you encounter a file reference below, use your Read tool to load it on a need-to-know basis.

- 新功能：@sdd/workflows/new-feature.md
- Bug 修復：@sdd/workflows/bug-fix.md
- 重構：@sdd/workflows/refactoring.md
- 技術探索：@sdd/workflows/spike.md
- 規格變更：@sdd/workflows/change-request.md

## 程式碼品質要求

- 遵循專案既有的程式碼風格和架構模式
- 新增程式碼必須有對應的測試
- 不引入已知的安全漏洞（參照 OWASP Top 10）
- 保持函式單一職責，模組低耦合
- 命名清晰具描述性，減少不必要的註解

## AI 行為準則

- 實作前先確認規格是否存在
- 發現規格缺漏時，先補充規格再實作
- 遇到不確定的設計決策，建議建立 ADR
- 不擅自添加規格外的功能或「順便優化」
- 不做規格外的「順便改善」— 額外變更需要額外的規格
- 遇到規格不明確的部分，先更新規格再實作

## 詳細規則

CRITICAL: Read the following instruction files as they are relevant to all workflows:

- 編碼規範：@.github/instructions/coding-standards.instructions.md
- SDD 流程規則：@.github/instructions/sdd-process.instructions.md
- 安全準則：@.github/instructions/security.instructions.md
