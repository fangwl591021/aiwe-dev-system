# Git Rules

## 分支與提交

- `main` 保持可用。
- 重要功能使用功能分支。
- Commit 訊息應描述目的。
- 一個 Commit 儘量只處理一類變更。
- 大型改動先建立 PR。
- 緊急小修可直接處理，但仍需記錄 `CHANGELOG.md`。

## 不應提交

- 自動產生檔案。
- Secret、Token、密碼。
- 真實 `.env`。
- 本機暫存檔。
- 與任務無關的大量格式化變更。

## 建議 Commit 格式

```text
feat: add LINE login callback
fix: prevent duplicate booking
docs: update deployment guide
refactor: extract API error handler
chore: update configuration
test: add booking validation tests
```
