# Modules

`modules/` 保存已經真實專案驗證、可以搬到其他 Repository 的實作索引。

## Current Status

Status: Experimental
Verified projects: BookingOS only
Production reusable: No

第一階段只建立文件骨架，不假裝模組已經完成。任何尚未在兩個產品驗證的模組，都不得標記為 production reusable。

## 正式模組門檻

正式模組應包含：

- 安裝方式。
- 相依套件。
- 環境變數。
- 使用範例。
- 測試方式。
- 適用範圍。
- 限制。
- 至少兩個產品的驗證紀錄。

## 禁止事項

- 不得將 BookingOS 程式複製到 `modules/`。
- 不得提交 Secret、LIFF ID、正式客戶資料、正式 Tenant 資料或完整 Migration 程式。
- 未經兩個產品驗證前，只能標記為 Experimental。