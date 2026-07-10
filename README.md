# AIWE Dev System

AIWE Dev System 是 Tony 所有 AI 開發專案共用的開發控制中心。它保存共用開發規範、架構模式、研究成果、驗收模板、Prompt 庫、案例復盤，以及尚在驗證中的可重用模組索引。

## 它是什麼

本 Repository 用來：

- 保存跨專案的開發規範。
- 保存可重複使用的技術知識與研究成果。
- 保存經過驗證或正在驗證的 LINE、Cloudflare、API、SaaS booking 架構模式。
- 建立 ChatGPT、Tony、Codex 三方共用的專案管理流程。
- 建立可複製的驗收模板與 release gate。
- 保存案例復盤，降低每次重新研究、重新設定與重新說明的成本。
- 作為各產品 Repository 的文件與流程來源。

## 它不是什麼

本 Repository 不是：

- WordPress 母站。
- 單一 SaaS。
- 所有產品共用的執行後端。
- 所有產品程式碼的大型 Monorepo。
- 需要部署上線的 Web App。
- BookingOS 或任何產品的程式碼倉庫。

## 架構原則

> 產品獨立，規範共用，知識沉澱，模組可移植。

每個產品都應擁有獨立 Repository、獨立部署與獨立環境變數，例如：

- 預約服務通 / BookingOS
- AI 智能名片
- AI 換眼鏡
- LINE OA 工具

本 Repo 只保存共用規範、模板、文件、技術筆記、研究成果、案例復盤及經過驗證的模組使用方法，不直接放入各產品完整程式碼。

## 導覽

### Rules

- `rules/`：跨專案開發、安全、API、Git、文件、重用與 acceptance-first 硬性規則。
- SaaS booking 相關硬性規則：
  - `rules/PRODUCT_FLOW_BEFORE_ARCHITECTURE.md`
  - `rules/NO_SHARED_LOGIN_ROUTING.md`
  - `rules/EXTERNAL_AUTH_IS_OPTIONAL.md`
  - `rules/REAL_DEVICE_ACCEPTANCE_REQUIRED.md`

### Workflow

- `workflow/`：新專案、生命週期、Codex 任務、Review 與結案流程。

### Architecture

- `architecture/saas-booking/`：SaaS 預約產品的路由、tenant、identity、booking domain、availability、session boundary、LINE optional provider 模式。
- 固定入口：
  - `/store/{slug}` = Customer
  - `/merchant/{slug}` = Merchant
  - `/platform` = Platform Admin

### Research

- `research/booking-systems/`：Easy!Appointments、LibreBooking、Cal.diy、Thunderbird Appointment 的開源預約系統研究與比較。

### Templates

- `templates/`：可複製到產品 Repo 的專案文件模板。
- `templates/acceptance/`：Customer、Merchant、Platform、Mobile、Release Gate 驗收 checklist。

### Case Studies

- `case-studies/BookingOS/`：BookingOS 案例復盤、架構決策、Customer Login Failure Review、開源參考對照與可重用教訓。
- Case Study 不得包含 Secret、LIFF ID、正式客戶資料、產品原始碼、正式 Tenant 資料或完整 Migration 程式。

### Prompts

- `prompts/`：可直接交給 Codex 使用的任務 Prompt。

### Experimental Modules

- `modules/`：尚在驗證中的模組索引。
- 尚未在兩個產品驗證前，模組必須標記：
  - `Status: Experimental`
  - `Verified projects: BookingOS only`
  - `Production reusable: No`

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

## 使用方式

開始新產品時，先閱讀 `workflow/START_NEW_PROJECT.md`，再複製 `templates/` 中必要文件到產品 Repo。涉及 SaaS 預約、登入、session、tenant、migration 或 LINE/Google/Apple auth 時，必須先閱讀 `architecture/saas-booking/` 與新增的 acceptance-first rules。