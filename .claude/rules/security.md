# 安全準則

## OWASP Top 10 檢查清單

### 1. 存取控制缺陷（Broken Access Control）
- 預設拒絕所有存取
- 實施適當的角色權限檢查
- 不僅依賴前端驗證
- 每個 API 端點都要檢查授權

### 2. 加密機制失效（Cryptographic Failures）
- 敏感資料傳輸使用 TLS
- 密碼使用 bcrypt/argon2 雜湊，不使用 MD5/SHA1
- 不在日誌中記錄敏感資訊
- 金鑰和密碼使用環境變數或金鑰管理服務

### 3. 注入攻擊（Injection）
- SQL：使用參數化查詢或 ORM
- XSS：輸出編碼、使用 CSP
- 命令注入：避免直接執行系統命令，必要時使用白名單
- 路徑遍歷：驗證並正規化檔案路徑

### 4. 不安全設計（Insecure Design）
- 使用威脅模型分析
- 實施速率限制
- 驗證業務邏輯流程

### 5. 安全設定缺陷（Security Misconfiguration）
- 移除預設帳號和密碼
- 禁用不必要的功能和端口
- 設定適當的安全標頭

### 6. 易受攻擊的元件（Vulnerable Components）
- 定期更新依賴套件
- 使用已知漏洞掃描工具
- 移除未使用的依賴

### 7. 身份驗證與認證失效（Authentication Failures）
- 實施多因素認證
- 強密碼政策
- 會話管理：適當的過期時間、安全的 session ID

### 8. 軟體與資料完整性失效（Integrity Failures）
- 驗證外部資料來源
- CI/CD 管線安全
- 使用程式碼簽章

### 9. 安全日誌與監控不足（Logging Failures）
- 記錄所有認證事件
- 記錄存取控制失敗
- 不記錄敏感資料

### 10. SSRF（Server-Side Request Forgery）
- 驗證並限制外部 URL
- 使用白名單限制可存取的服務
- 不將內部服務暴露於使用者可控的請求中

## 審查時的安全檢查

在 Code Review 時，對照以上項目逐一檢查。發現安全問題時，標記為 **SECURITY** 並說明風險等級和修復建議。
