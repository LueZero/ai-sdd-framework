# 編碼規範

> **注意**：這是框架預設的通用規範，請根據你的專案技術棧進行客製化。

## 通用規範

### 命名
- 使用描述性名稱，避免縮寫（除非是廣為人知的慣例）
- 函式名稱使用動詞開頭：`createUser`, `validateInput`, `fetchOrders`
- 布林值使用 `is/has/can/should` 前綴：`isActive`, `hasPermission`
- 常數使用 UPPER_SNAKE_CASE
- 類別/型別使用 PascalCase
- 函式/變數使用 camelCase 或 snake_case（依專案慣例）

### 函式設計
- 單一職責：一個函式只做一件事
- 參數不超過 3 個，超過則使用物件參數
- 避免副作用，優先使用純函式
- 提早回傳（early return）減少巢狀

### 錯誤處理
- 在系統邊界驗證輸入
- 使用具體的錯誤類型，不使用通用錯誤
- 錯誤訊息包含上下文資訊
- 不吞掉錯誤（catch 後不處理）

### 安全性
- 不將敏感資訊寫死在程式碼中
- 所有外部輸入視為不可信
- 使用參數化查詢，防止注入攻擊
- 遵循最小權限原則

## 客製化指南

在此檔案中加入你的專案特定規範，例如：

```markdown
## TypeScript 專案規範
- 使用 strict mode
- 優先使用 interface 而非 type alias
- 使用 enum 時考慮 const enum

## Python 專案規範
- 遵循 PEP 8
- 使用 type hints
- 使用 dataclass 或 pydantic model

## Go 專案規範
- 遵循 Effective Go
- 錯誤處理不使用 panic
- 使用 context 傳遞請求範圍的值
```
