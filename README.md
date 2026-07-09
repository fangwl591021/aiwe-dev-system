# AIWE Dev System

AIWE Dev System 是 Tony 所有 AI 開發專案共用的開發控制中心。它保存跨專案的開發規範、技術知識、Prompt 庫、專案文件模板，以及已經驗證過且未來可移植的模組索引。

## 它是什麼

本 Repository 用來：

- 保存跨專案的開發規範。
- 保存可重複使用的技術知識。
- 保存經過驗證的 LINE、Cloudflare、API 串接方式。
- 建立 ChatGPT、Tony、Codex 三方共用的專案管理流程。
- 降低每次建立新專案時重新研究、重新設定與重新說明的成本。
- 作為各產品 Repository 的文件與流程來源。

## 它不是什麼

本 Repository 不是：

- WordPress 母站。
- 單一 SaaS。
- 所有產品共用的執行後端。
- 所有產品程式碼的大型 Monorepo。
- 需要部署上線的 Web App。

## 架構原則

> 產品獨立，規範共用，知識沉澱，模組可移植。

每個產品都應擁有獨立 Repository、獨立部署與獨立環境變數，例如：

- 預約服務通
- AI 智能名片
- AI 換眼鏡
- LINE OA 工具

本 Repo 只保存共用規範、模板、文件、技術筆記及經過驗證的模組使用方法，不直接放入各產品完整程式碼。

## 三方角色

### Tony

- 決定產品方向。
- 確認商業需求。
- 排定優先順序。
- 驗收使用流程。

### ChatGPT

- 協助需求整理。
- 架構與流程分析。
- 任務拆解。
- 文件與驗收條件設計。
- 協助 Code Review。

### Codex

- 讀取 Repo 文件。
- 分析現有程式。
- 執行明確任務。
- 編寫與修改程式。
- 執行測試。
- 更新專案狀態文件。
- 回報風險及尚未完成事項。

## 主要目錄

- `rules/`：跨專案開發、安全、API、Git、文件與重用規則。
- `workflow/`：新專案、生命週期、Codex 任務、Review 與結案流程。
- `templates/`：可複製到產品 Repo 的專案文件模板。
- `knowledge/`：技術理解、設定流程、限制與排查紀錄。
- `modules/`：已驗證且可移植的模組索引。第一版只建立佔位文件。
- `projects/`：產品索引，不保存產品完整程式碼。
- `prompts/`：可直接交給 Codex 使用的任務 Prompt。

## 使用方式

開始新產品時，先閱讀 `workflow/START_NEW_PROJECT.md`，再複製 `templates/` 中必要文件到產品 Repo。每次交給 Codex 任務前，請先確認產品 Repo 已有專案文件，並在任務中給出清楚的驗收條件。
