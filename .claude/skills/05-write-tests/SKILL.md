---
name: 05-write-tests
description: "撰寫測試：依照規格書的驗收條件撰寫測試計劃和測試程式碼。在實作完成後需要驗證功能時使用。"
context: fork
agent: sdd-developer
argument-hint: "參照規格文件，例如 SPEC-001"
---

# Phase 5: 撰寫測試

依據規格書的驗收條件，撰寫測試程式碼。

## 前置條件
- 功能規格書已完成
- 實作程式碼已完成
- 瞭解專案使用的測試框架

## 步驟

### 1. 建立測試計劃

參考 `sdd/templates/test-plan.tmpl.md` 範本。

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
