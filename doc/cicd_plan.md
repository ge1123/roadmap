# CI/CD 與 DevOps 工作流學習計畫

[待辦事項](../todo/cicd_plan.md)

## 目標
- 建立從原始碼到部署的自動化流程，縮短交付 Lead Time
- 了解版本治理、流水線安全與環境一致性
- 熟悉 GitHub Actions、Azure DevOps/YAML Pipeline 與 Infrastructure as Code

## 核心主題
- Branch 策略、語意化版本、Git Hooks
- Build/測試/掃描/封裝/部署 Pipeline 設計與可重用 Templates
- Secrets 管理（GitHub OIDC、Azure Key Vault、AWS Secrets Manager）
- Infrastructure as Code：Bicep、Terraform、Pulumi
- 發布策略：藍綠部署、金絲雀、Feature Flags、Rollback 流程

## 實作路線
1. 建立 GitHub Actions Workflow：Restore → Build → Test → Report → Publish Artifact
2. 串接安全掃描（dotnet format、dotnet list package --vulnerable、Trivy、Dependabot）
3. 以 Terraform/Bicep 佈建測試環境（App Service / ECS / AKS）
4. 透過多階段部署（DEV/QA/PROD）與手動審核 Gate 管控
5. 新增監控與通知（GitHub Checks、Slack/Webhook、Teams）

## 產出
- 可重用的 YAML Pipeline 模板與部署腳本
- IaC 範例專案（環境與資源定義）
- 部署流水線儀表板與執行紀錄

## 工具與資源
- GitHub Actions、Azure DevOps Pipelines、GitLab CI（可比較）
- Terraform、Azure Bicep、Pulumi
- Trivy、OWASP Dependency-Check、dotnet format、Super-Linter
