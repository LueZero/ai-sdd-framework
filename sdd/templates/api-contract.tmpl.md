# API 契約：[API 名稱]

> **關聯規格**：SPEC-{編號}
> **版本**：v1.0
> **最後更新**：{日期}

## 1. 概述

<!-- 這組 API 的目的和使用情境 -->

## 2. 基本資訊

- **Base URL**：`/api/v1`
- **認證方式**：Bearer Token / API Key / Session
- **Content-Type**：`application/json`

## 3. 端點定義

### 3.1 [操作名稱]

```
[METHOD] /path/{param}
```

**描述**：

**權限**：

#### 請求

**路徑參數：**
| 參數 | 型別 | 必填 | 說明 |
|------|------|------|------|
|      |      |      |      |

**查詢參數：**
| 參數 | 型別 | 必填 | 預設值 | 說明 |
|------|------|------|-------|------|
|      |      |      |       |      |

**請求主體：**
```json
{
  "field": "type — description"
}
```

#### 回應

**成功回應 (200)：**
```json
{
  "field": "type — description"
}
```

**錯誤回應：**
| 狀態碼 | 錯誤碼 | 說明 | 觸發條件 |
|-------|-------|------|---------|
| 400   |       |      |         |
| 401   |       |      |         |
| 403   |       |      |         |
| 404   |       |      |         |
| 422   |       |      |         |

#### 範例

**請求：**
```bash
curl -X POST /api/v1/path \
  -H "Authorization: Bearer {token}" \
  -H "Content-Type: application/json" \
  -d '{"field": "value"}'
```

**回應：**
```json
{
  "field": "value"
}
```

---

### 3.2 [下一個端點]

<!-- 重複上述結構 -->

## 4. 通用錯誤格式

```json
{
  "error": {
    "code": "ERROR_CODE",
    "message": "Human-readable message",
    "details": {}
  }
}
```

## 5. 分頁格式（如適用）

```json
{
  "data": [],
  "pagination": {
    "page": 1,
    "pageSize": 20,
    "totalItems": 100,
    "totalPages": 5
  }
}
```

## 6. 速率限制

| 端點 | 限制 | 視窗 |
|------|------|------|
|      |      |      |

## 7. 變更記錄

| 版本 | 日期 | 變更內容 |
|------|------|---------|
| v1.0 |      | 初始版本 |
