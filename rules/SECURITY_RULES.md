# Security Rules

## Secret 與環境變數

- Secret 只能放在環境變數或平台 Secret。
- 建立 `.env.example`，不得提交真實 `.env`。
- 前端不可保存伺服器端 Secret。
- 正式與測試環境必須分離。

## 權限與驗證

- Webhook 必須驗證簽章。
- 採用最小權限原則。
- CORS、輸入驗證、權限驗證不可省略。
- 權限判斷應在伺服器端完成。

## 資料保護

- 敏感資料不得寫入 Log。
- 個資欄位應最少化。
- 錯誤回應不得洩漏內部堆疊、Token、Secret 或資料庫細節。
