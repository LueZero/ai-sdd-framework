---
description: 系統設計 — 根據規格書設計架構、元件拆解、撰寫 ADR
agent: sdd-architect
subtask: true
---

# Phase 3: 系統設計

根據功能規格書，設計系統架構。

## 前置條件
- 對應的功能規格書已存在（`docs/sdd/specs/`）
- 專案上下文文件已建立（`docs/sdd/project-context.md`）

## 步驟

### 1. 閱讀規格
- 完整閱讀對應的功能規格書
- 理解所有驗收條件
- 確認非功能需求

### 2. 元件設計

參考 `sdd/templates/system-design.tmpl.md` 範本。

- 識別需要的模組/元件
- 定義元件之間的介面
- 確認資料流方向
- 設計錯誤處理策略

### 3. 技術決策

對於每個重大技術選擇，建立 ADR（Architecture Decision Record）：

參考 `sdd/templates/adr.tmpl.md` 範本。

- 選擇了什麼？為什麼？
- 考慮過哪些替代方案？
- 有什麼取捨（trade-offs）？

### 4. 介面定義

如果涉及 API，參考 `sdd/templates/api-contract.tmpl.md`：
- 端點定義
- 請求/回應格式
- 錯誤碼定義
- 認證/授權方式

如果涉及 UI 元件，參考 `sdd/templates/component-spec.tmpl.md`：
- 元件階層
- Props/State 定義
- 事件處理

### 5. 資料模型設計

參考 `sdd/templates/data-model.tmpl.md`：
- Entity 定義
- 關聯關係
- 索引策略

### 6. 儲存設計文件

- 系統設計 → `docs/sdd/designs/DESIGN-{編號}-{名稱}.md`
- ADR → `docs/sdd/decisions/ADR-{編號}-{主題}.md`

$ARGUMENTS
