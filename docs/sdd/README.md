# SDD 產出物

此目錄存放由 SDD 流程產出的文件。

## 目錄結構

```
docs/sdd/
├── specs/          # 功能規格書
├── designs/        # 系統設計文件
├── decisions/      # 架構決策記錄（ADR）+ Spike 結論
└── test-plans/     # 測試計劃
```

## 命名規範

- 規格書：`SPEC-{三位數編號}-{功能名稱}.md`
- 設計文件：`DESIGN-{三位數編號}-{功能名稱}.md`
- ADR：`ADR-{三位數編號}-{決策主題}.md`
- 測試計劃：`TEST-{三位數編號}-{功能名稱}.md`
- Bug 修復：`BUG-{三位數編號}-{描述}.md`
- 重構：`REFACTOR-{三位數編號}-{描述}.md`
- 技術探索：`SPIKE-{三位數編號}-{主題}.md`

## 範例

```
docs/sdd/
├── specs/
│   ├── SPEC-001-user-authentication.md
│   └── SPEC-002-order-management.md
├── designs/
│   ├── DESIGN-001-user-authentication.md
│   └── DESIGN-002-order-management.md
├── decisions/
│   ├── ADR-001-jwt-vs-session.md
│   └── SPIKE-001-redis-evaluation.md
└── test-plans/
    ├── TEST-001-user-authentication.md
    └── TEST-002-order-management.md
```
