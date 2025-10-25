# CI/CD 與 DevOps 待辦清單

[筆記](../note/cicd_plan.md)

## 理解與調研
- [ ] 盤點現有專案流程，整理 Build、Test、Artifact 需求與痛點。
- [ ] 研究 GitHub Actions、Azure DevOps YAML 語法差異，記錄常用關鍵字與最佳實務。
- [ ] 閱讀 Trivy、Dependabot、`dotnet format` 官方文件，確認使用限制與輸出格式。

## 設計與演練
- [ ] 選定一個 .NET 範例專案，設計 Restore → Build → Test → Publish Artifact 的基本流程圖。
- [ ] 規劃 DEV/QA/PROD 多階段部署策略，界定審核 Gate、通知節點與回滾條件。
- [ ] 撰寫 IaC 模板（Terraform 或 Bicep），描述需建立的雲端資源與變數。

## 實作與驗證
- [ ] 實作 GitHub Actions Workflow，完成 Restore → Build → Test → Publish Artifact 並截圖紀錄。
- [ ] 串接程式碼品質與安全掃描（`dotnet format`、`dotnet list package --vulnerable`、Trivy），確保 PR 產出報告。
- [ ] 以 Terraform 或 Bicep 佈建最小可行的測試環境，並提交 state 管理規則。
- [ ] 建立通知與監控（GitHub Checks、Slack 或 Teams Webhook），測試部署失敗時會觸發警示。

## 回顧與強化
- [ ] 紀錄流水線調整前後的 Lead Time、失敗率與回滾耗時，撰寫回顧報告。
- [ ] 持續優化 Template 可重用性，將參數化、條件式部署與共用步驟整理成文件。
- [ ] 蒐集工具版本或授權需求，更新 `doc/cicd_plan.md` 的資源列表與注意事項。



---


## ✅ CI/CD 盤點清單（.NET 專案用）(對應盤點專案)
### 🧱 A. Build

- [ ] 需要的 **.NET SDK 版本**（例如：6 / 8 / 9）  
- [ ] 目標 **作業系統**（Windows / Linux）  
- [ ] 專案型別：
  - [ ] Web API
  - [ ] Class Library
  - [ ] Worker
  - [ ] Console
  - [ ] UI（WPF / WinUI）
- [ ] 是否使用 **私有 NuGet 源 / 內部 feed**
- [ ] 平均建置時間（單位：分鐘）  
- [ ] 是否存在 **長鏈式還原 / 熱點專案**
- [ ] 需要的 **環境變數 / 密鑰**（例如連線字串）  
  - [ ] 是否可放入 **GitHub Secrets**
- [ ] 版本號規則：
  - [ ] SemVer（例如 1.2.3）
  - [ ] tag 驅動（例如 `v1.2.3`）
  - [ ] 手動寫死於 `csproj`

---
### 🧪 B. Test

- [ ] 使用的測試框架：
  - [ ] xUnit
  - [ ] NUnit
  - [ ] MSTest
- [ ] 各專案測試覆蓋情況（需列出）
- [ ] 覆蓋率工具：
  - [ ] coverlet.collector
  - [ ] coverlet.console  
  - [ ] 覆蓋率門檻（％）：______
- [ ] 整合測試依賴：
  - [ ] 資料庫
  - [ ] 外部 API
  - [ ] 容器（Docker Compose / Testcontainers）
- [ ] Flaky tests（不穩定測試）清單  
- [ ] 測試時間分佈（>5 分鐘的套件請標記）

---

### 📦 C. Artifact

- [ ] 產出項目：
  - [ ] NuGet 套件（`.nupkg`）
  - [ ] Docker Image
  - [ ] 可部署包（zip、單檔 exe、Self-Contained）
  - [ ] 前端資產（Full-stack 專案）
  - [ ] SBOM / 授權報表
- [ ] 發佈節點：
  - [ ] NuGet.org / 私庫
  - [ ] GHCR / Docker Hub
  - [ ] GitHub Release 資產
  - [ ] S3 / Blob Storage
- [ ] 版本推進策略：
  - [ ] PR → main：僅快取 / 測試
  - [ ] tag 或 Release：才進行發佈

---

### ⚠️ 常見痛點清單

- [ ] 建置速度慢（NuGet 還原、跨解決方案依賴）
- [ ] 測試覆蓋率缺失
- [ ] 私庫憑證管理混亂
- [ ] 發佈物不一致（包格式或命名差異）
- [ ] 不同專案使用不同 SDK
- [ ] 版本號手動維護（容易出錯）
