# API Rules

本文件定義 AIWE 專案建議採用的 API 基本格式。各產品可依實際需求調整，但應保持一致、可排查、可驗證。

## 成功格式

```json
{
  "success": true,
  "data": {},
  "meta": {}
}
```

## 失敗格式

```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Human readable message",
    "details": {}
  }
}
```

## API 要求

- 使用合理的 HTTP Status Code。
- 輸入資料必須驗證。
- 錯誤訊息不得洩漏 Secret 或內部堆疊。
- 外部 API 必須設定 Timeout。
- Retry 只能用於適合重試的錯誤。
- 涉及重複送出的操作要考慮 Idempotency。
- API 串接必須記錄必要 Log。
- 不把外部平台的原始錯誤直接顯示給一般使用者。
