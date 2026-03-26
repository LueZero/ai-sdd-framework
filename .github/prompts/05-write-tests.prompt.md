---
description: "Write tests based on SDD specifications. Creates test plan and test code covering acceptance criteria, edge cases, and error scenarios."
agent: "sdd-developer"
argument-hint: "Reference the spec file, e.g., SPEC-001"
---

# Phase 5: 撰寫測試

依據規格書的驗收條件，撰寫測試程式碼。

## 前置條件
- 功能規格書已完成
- 實作程式碼已完成
- 瞭解專案使用的測試框架

## 步驟

### 1. 建立測試計劃

參考 [test-plan.tmpl.md](../../sdd/templates/test-plan.tmpl.md) 範本。

從規格書的驗收條件出發：
- 將每個驗收條件轉換為一或多個測試案例
- 補充邊界情境測試
- 補充錯誤處理測試
- 儲存至 `docs/sdd/test-plans/TEST-{編號}-{功能名}.md`

### 2. 撰寫測試

#### 測試分層

```
單元測試（Unit Tests）
├── 純函式邏輯
├── 業務規則
└── 資料轉換

整合測試（Integration Tests）
├── API 端點
├── 資料庫操作
└── 外部服務整合

端到端測試（E2E Tests）— 如適用
├── 使用者流程
└── 關鍵業務路徑
```

#### 測試結構

每個測試遵循 AAA（Arrange-Act-Assert）模式：

```
Arrange: 準備測試資料和前置條件
Act:     執行被測試的行為
Assert:  驗證結果符合預期
```

### 3. 測試命名

使用描述性名稱，清楚說明測試情境：
```
should_[預期行為]_when_[條件]
given_[前提]_when_[動作]_then_[結果]
```

### 4. 覆蓋率檢查

確保測試覆蓋：
- [ ] 所有規格中的驗收條件
- [ ] 正常流程（happy path）
- [ ] 替代流程（alternative path）
- [ ] 錯誤情境（error cases）
- [ ] 邊界值（boundary values）
- [ ] 空值/缺值處理

### 5. 執行測試

- 確認所有測試通過
- 檢查測試執行時間是否合理
- 確認沒有測試間的相依性

## 測試品質原則

- **獨立**：每個測試獨立運行，不依賴其他測試
- **可重複**：每次執行結果一致
- **快速**：單元測試應在毫秒級完成
- **可讀**：測試即文件，從測試名稱就能理解行為
- **對照規格**：每個測試都能追溯到規格中的驗收條件
