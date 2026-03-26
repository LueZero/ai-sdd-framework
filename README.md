# AI-SDD Framework

> **Specification-Driven Development × AI Coding** — 一套可攜式、技術中立的 AI 輔助開發流程框架

## 什麼是 AI-SDD？

AI-SDD（AI-assisted Specification-Driven Development）是一套開源開發流程框架，透過結構化的規格驅動開發方法論，搭配 GitHub Copilot 的客製化系統（Agents、Prompts、Instructions、Skills），讓 AI 從「隨機回答」變成「按流程執行」。

**核心理念**：先定義規格，再讓 AI 依規格實作，全程可追蹤、可驗證。

## 為什麼需要這套框架？

| 問題 | AI-SDD 解法 |
|------|-------------|
| AI 寫出的程式碼風格不一致 | 統一的 Instructions 規範 |
| 需求溝通不精確，AI 理解偏差 | SDD 規格文件消除歧義 |
| 每次提示都要重新描述上下文 | Agents 和 Skills 自動注入上下文 |
| 沒有系統化流程，品質不穩定 | 7 階段 Prompt 鏈確保流程完整 |
| 框架綁定特定技術棧 | 技術中立設計，任何專案可用 |

## 快速開始

### 1. 複製框架到你的專案

```bash
# 方法一：Clone 後複製
git clone https://github.com/LueZero/ai-sdd-framework.git
cp -r ai-sdd-framework/.github your-project/
cp -r ai-sdd-framework/sdd your-project/
cp ai-sdd-framework/CLAUDE.md your-project/  # 可選：支援 Claude Code

# 方法二：作為 Git submodule
git submodule add https://github.com/LueZero/ai-sdd-framework.git .ai-sdd
```

### 2. 初始化你的專案

在 VS Code 中使用 GitHub Copilot Chat，輸入：
```
/01-init-project
```

這會分析你的專案結構，並生成專案特定的配置。

### 3. 開始開發

依照 [SDD 開發流程](#sdd-開發流程) 的 7 個階段進行開發。

## SDD 開發流程

```
┌─────────────────────────────────────────────────────────┐
│                    AI-SDD 開發流程                         │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  Phase 1        Phase 2        Phase 3        Phase 4   │
│  ┌──────┐      ┌──────┐      ┌──────┐      ┌──────┐   │
│  │ 初始化 │ ──→ │ 規格化 │ ──→ │ 設計  │ ──→ │ 實作  │   │
│  └──────┘      └──────┘      └──────┘      └──────┘   │
│  分析專案        撰寫規格        架構設計        按規格編碼 │
│  建立上下文      定義契約        元件拆解        生成程式碼 │
│                                                         │
│  Phase 5        Phase 6        Phase 7                   │
│  ┌──────┐      ┌──────┐      ┌──────┐                   │
│  │ 測試  │ ──→ │ 審查  │ ──→ │ 迭代  │ ──→ 完成 ✓       │
│  └──────┘      └──────┘      └──────┘                   │
│  撰寫測試        程式碼審查      精煉優化                  │
│  驗證規格        安全檢查        文件更新                  │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

| 階段 | Prompt 指令 | Agent | 產出 |
|------|------------|-------|------|
| Phase 1: 初始化 | `/01-init-project` | `@sdd-pm` | 專案上下文文件 |
| Phase 2: 規格化 | `/02-write-spec` | `@sdd-pm` | 功能規格書 |
| Phase 3: 設計 | `/03-design-system` | `@sdd-architect` | 系統設計文件 + ADR |
| Phase 4: 實作 | `/04-implement` | `@sdd-developer` | 原始碼 |
| Phase 5: 測試 | `/05-write-tests` | `@sdd-developer` | 測試程式碼 + 測試計劃 |
| Phase 6: 審查 | `/06-review` | `@sdd-reviewer` | 審查報告 |
| Phase 7: 迭代 | `/07-iterate` | 依需求 | 優化後的程式碼 |

## 框架結構

```
your-project/
├── .github/
│   ├── copilot-instructions.md          # 全域 AI 行為指引
│   ├── instructions/
│   │   ├── sdd-process.instructions.md  # SDD 流程規則
│   │   ├── coding-standards.instructions.md  # 編碼規範（可客製）
│   │   └── security.instructions.md     # 安全準則
│   ├── prompts/
│   │   ├── 01-init-project.prompt.md    # 7 個階段的 Prompt 鏈
│   │   ├── 02-write-spec.prompt.md
│   │   ├── 03-design-system.prompt.md
│   │   ├── 04-implement.prompt.md
│   │   ├── 05-write-tests.prompt.md
│   │   ├── 06-review.prompt.md
│   │   └── 07-iterate.prompt.md
│   ├── agents/
│   │   ├── sdd-architect.agent.md       # 架構師 Agent
│   │   ├── sdd-developer.agent.md       # 開發者 Agent
│   │   ├── sdd-reviewer.agent.md        # 審查者 Agent
│   │   └── sdd-pm.agent.md              # 產品經理 Agent
│   └── skills/
│       └── sdd-workflow/
│           ├── SKILL.md                 # SDD 工作流技能
│           └── references/
│               └── sdd-methodology.md   # SDD 方法論參考
├── sdd/
│   ├── templates/                       # SDD 文件範本
│   │   ├── feature-spec.tmpl.md
│   │   ├── api-contract.tmpl.md
│   │   ├── component-spec.tmpl.md
│   │   ├── data-model.tmpl.md
│   │   ├── system-design.tmpl.md
│   │   ├── adr.tmpl.md
│   │   └── test-plan.tmpl.md
│   └── workflows/                       # 工作流指南
│       ├── new-feature.md
│       ├── bug-fix.md
│       ├── refactoring.md
│       └── spike.md
├── docs/sdd/                            # SDD 產出物（每個專案生成）
│   ├── specs/
│   ├── designs/
│   ├── decisions/
│   └── test-plans/
└── CLAUDE.md                            # Claude Code 支援（可選）
```

## 工作流類型

框架支援 4 種開發情境，每種有對應的工作流指南：

| 工作流 | 適用情境 | 涵蓋階段 |
|--------|---------|---------|
| [新功能開發](sdd/workflows/new-feature.md) | 從零開始的功能 | Phase 1-7 完整流程 |
| [Bug 修復](sdd/workflows/bug-fix.md) | 生產環境問題 | Phase 2, 4-6 精簡流程 |
| [重構](sdd/workflows/refactoring.md) | 改善既有程式碼 | Phase 2-3, 4-6 |
| [技術探索](sdd/workflows/spike.md) | 研究與原型 | Phase 1-3 探索流程 |

## 客製化

### 調整編碼規範

編輯 `.github/instructions/coding-standards.instructions.md`，加入你的專案規範：

```markdown
## 你的專案規範
- 使用 TypeScript strict mode
- React 元件使用 functional components
- API 使用 RESTful 風格
```

### 新增專案特定模板

在 `sdd/templates/` 中新增你的模板。

### 擴充 Agent

在 `.github/agents/` 中新增專屬 Agent。

## 與其他 AI 工具整合

| 工具 | 支援方式 |
|------|---------|
| GitHub Copilot | 完整支援（Instructions + Agents + Prompts + Skills）|
| Claude Code | 透過 CLAUDE.md 支援 |
| Cursor | 透過 .cursorrules 支援（可從 copilot-instructions.md 轉換）|

## 設計原則

1. **規格先行** — 每個變更都從規格開始，不是從程式碼開始
2. **AI 即夥伴** — AI 遵循結構化指令，不是隨機提示
3. **可追蹤性** — 每行程式碼都映射回規格文件
4. **技術中立** — 不綁定任何語言或框架
5. **漸進採用** — 可以只用部分功能，不需全部導入

## 授權

MIT License
