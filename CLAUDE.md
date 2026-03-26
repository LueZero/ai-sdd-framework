# User Memory

本專案使用 AI-SDD（Specification-Driven Development）流程進行開發。

## SDD 流程

所有功能開發遵循 7 階段流程：初始化 → 規格化 → 設計 → 實作 → 測試 → 審查 → 迭代

## 核心規則

1. **規格先行**：實作前必須有規格文件（`docs/sdd/specs/`）
2. **不做規格外的事**：嚴格按規格實作，不擅自添加功能
3. **可追蹤性**：每段程式碼映射到規格中的驗收條件
4. **測試驗證**：每個驗收條件都有對應的測試

## 文件位置

- 規格書：`docs/sdd/specs/SPEC-{編號}-{名稱}.md`
- 設計文件：`docs/sdd/designs/DESIGN-{編號}-{名稱}.md`
- ADR：`docs/sdd/decisions/ADR-{編號}-{主題}.md`
- 測試計劃：`docs/sdd/test-plans/TEST-{編號}-{名稱}.md`
- 範本：`sdd/templates/`

## 開發流程

- 新功能：參照 `sdd/workflows/new-feature.md`
- Bug 修復：參照 `sdd/workflows/bug-fix.md`
- 重構：參照 `sdd/workflows/refactoring.md`
- 技術探索：參照 `sdd/workflows/spike.md`

## AI 行為準則

- 實作前先確認規格是否存在
- 發現規格缺漏時，先補充規格再實作
- 遇到不確定的設計決策，建議建立 ADR
- 不擅自添加規格外的功能或「順便優化」
- 程式碼品質遵循 `.github/instructions/coding-standards.instructions.md`
- 安全性遵循 `.github/instructions/security.instructions.md`
