# 飯店 ERP 營運中台 — 專案資源清單

> VenueOS 外掛 ERP 的互動原型（閉環會計版）。VenueOS 管前台/會員/交易，這套 ERP 補後勤閉環（財務會計、應收應付、採購庫存、成本損益、人事薪資、三大會計報表）。
> 分工：需求交給 Claude Code → 改主檔 `index.html` → push GitHub + 重發同一 Artifact 網址。使用者不需碰程式碼。

---

## 互動 ERP Demo（現行版本）

| 項目 | 位置 |
|---|---|
| **公開網頁（給客戶看）** | https://gbi0426-terry.github.io/hotel-erp-demo/ |
| **私有 Artifact（分享連結，不變）** | https://claude.ai/code/artifact/7615803b-aa03-4aa4-ad79-16c402b3eec2 |
| **主檔／唯一源頭（要改就改這個）** | `/Users/a0000/Sites/hotel-erp-demo/index.html` |
| GitHub repo | https://github.com/gbi0426-Terry/hotel-erp-demo |
| 本機預覽 | `http://localhost:5101`（`.claude/launch.json` 名稱：`hotel-erp-demo`） |
| Artifact 轉出暫存檔 | `/private/tmp/claude-501/-Users-a0000-Sites/185cab03-a8a7-4002-8d11-09ef609826ae/scratchpad/VenueOS-ERP-Demo.html` |

### Demo 模組（ERP 閉環版）
ERP 總覽、VenueOS 同步、財務會計、應收帳款、應付帳款、採購管理、庫存管理、成本損益、人事薪資、會計報表、主檔管理、導入規劃。
- 互動：閉環 Demo 流程可逐步執行，KPI 卡／工作佇列可跳轉，表格每列可開明細彈窗，AR/AP 可收付款，採購可推進與驗收，庫存可扣料與請購。
- 報表：會計報表頁含損益表、資產負債表、現金流量表，示範 ERP 單據如何彙總為管理級財務報表。
- 資料：全部為**示範（假）資料**，無真實個資。

---

## 更新流程（給 Claude Code 的指示）

1. 改主檔 `/Users/a0000/Sites/hotel-erp-demo/index.html`。
2. 本機預覽驗證：`preview_start hotel-erp-demo`（port 5101），檢查 console 無錯。
3. **更新公開網頁**：
   ```
   git -C /Users/a0000/Sites/hotel-erp-demo add -A && git commit -m "更新" && git push
   ```
   約 1 分鐘後 https://gbi0426-terry.github.io/hotel-erp-demo/ 生效。
4. **更新 Artifact**：去外框轉出 → 取 `<style>…</style>` + `<body>` 內容 → 寫入 scratchpad 檔 → 呼叫 Artifact 工具用**同一個 file_path** → 重發到同一 URL。

> 規則：以本機 `index.html` 為唯一源頭。若曾在 claude.ai 網頁端改過，換回 Code 前先 WebFetch 抓回 Artifact 最新內容覆寫本機，避免覆蓋。

---

## 注意事項

- 舊 repo `venueos-erp-demo` 已**轉私有、Pages 已下線**（內容為過時舊版，僅保留存檔，不對外）。對外一律用上面的 `hotel-erp-demo`。
- 新 repo 從第一個 commit 就帶 `.nojekyll`，Pages 建置正常（舊 repo 的 legacy 建置卡住是 GitHub 端問題）。

## 相關文件（Word）

| 文件 | 位置 |
|---|---|
| 合併定稿（盤點與訪談） | `/Users/a0000/Sites/VenueOS_外掛ERP_盤點與訪談_合併定稿.docx` |
| python-docx 版 | `/Users/a0000/outputs/venueos_erp_review/VenueOS_外掛ERP_功能盤點與訪談清單.docx` |

## 客戶原系統（需登入）
- VenueOS 後台：https://www.hui-dun.com/mc/programs?prop=PROP-TEST-HOTEL&s=dashboard

---

_最後更新：2026-07-09_
