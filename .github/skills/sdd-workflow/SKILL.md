---
name: sdd-workflow
description: "Complete SDD (Specification-Driven Development) workflow orchestration. Use when starting a new feature, following SDD process, managing specs, designs, and implementation lifecycle. Covers project initialization, spec writing, architecture design, implementation, testing, review, and iteration."
argument-hint: "Describe what you want to build or which SDD phase to execute"
---

# SDD Workflow Skill

本技能提供完整的 SDD（Specification-Driven Development）工作流程導引。

## When to Use

- 開始一個新功能的開發
- 需要完整走過 SDD 流程（規格 → 設計 → 實作 → 測試 → 審查）
- 需要了解 SDD 流程的某個特定階段

## SDD 流程總覽

```
Phase 1: 初始化 (/01-init-project)
    ↓
Phase 2: 規格化 (/02-write-spec)
    ↓
Phase 3: 設計   (/03-design-system)
    ↓
Phase 4: 實作   (/04-implement)
    ↓
Phase 5: 測試   (/05-write-tests)
    ↓
Phase 6: 審查   (/06-review)
    ↓
Phase 7: 迭代   (/07-iterate)
    ↓
  完成 ✓
```

## Procedure

### 判斷起始階段

根據專案狀態選擇起點：

| 狀態 | 起始階段 |
|------|----------|
| 全新專案 | Phase 1 |
| 已有專案，新功能 | Phase 2 |
| 已有規格，需要設計 | Phase 3 |
| 已有設計，需要實作 | Phase 4 |
| 已有實作，需要測試 | Phase 5 |
| 需要 Code Review | Phase 6 |
| **規格需要變更** | `/08-change-request`（任意階段）|

### 執行流程

1. 確認當前階段的前置條件是否滿足
2. 使用對應的 Prompt 執行該階段
3. 確認產出物的品質
4. 前進到下一階段

### 文件位置

- 規格書：`docs/sdd/specs/SPEC-{編號}-{名稱}.md`
- 設計文件：`docs/sdd/designs/DESIGN-{編號}-{名稱}.md`
- ADR：`docs/sdd/decisions/ADR-{編號}-{主題}.md`
- 測試計劃：`docs/sdd/test-plans/TEST-{編號}-{名稱}.md`
- 變更請求：`docs/sdd/changes/CR-{編號}-{描述}.md`
- 範本：`sdd/templates/`
- 工作流指南：`sdd/workflows/`

### 專屬 Agent

| Agent | 角色 | 適用階段 |
|-------|------|---------|
| `@sdd-pm` | 產品經理 | Phase 1, 2, 變更管理 |
| `@sdd-architect` | 架構師 | Phase 3, 變更管理（設計類）|
| `@sdd-developer` | 開發者 | Phase 4, 5 |
| `@sdd-reviewer` | 審查者 | Phase 6 |

## Reference

- [SDD 方法論](./references/sdd-methodology.md)
