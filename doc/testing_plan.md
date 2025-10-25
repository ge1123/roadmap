# 測試與品質保障學習計畫

## 目標
- 建立涵蓋單元、整合、契約與端對端測試的完整策略
- 養成測試驅動與品質量測習慣，支援 CI/CD 自動化
- 熟悉測試資料、Mock、測試隔離與回歸分析流程

## 核心主題
- 測試金字塔與測試類型：Unit、Integration、Contract、E2E
- 資料驅動測試與 Bogus/AutoFixture 造數據技巧
- Mock/Stubs/Fakes 與 Testcontainers、WireMock.Net 等環境模擬
- Coverage、Mutation Testing、靜態分析（SonarQube、dotnet analyzers）
- QA 核心指標（Lead Time、MTTR、品質閥值）與報表自動化

## 實作路線
1. 使用 xUnit + FluentAssertions 重構既有單元測試，導入 TestData Builders
2. 建立整合測試專案：透過 Testcontainers 啟動 SQL Server / Redis / Message Broker
3. 套用 Pact 或 Microsoft.Playwright 進行契約/E2E 測試，並串入 CI Pipeline
4. 設定 Coverlet、ReportGenerator、Stryker.NET（Mutation）監控品質門檻

## 產出
- 測試策略文件（包含金字塔比例與品質指標）
- 自動化測試專案範例（Unit、Integration、Contract、E2E）
- 品質儀表板（Coverage、Mutation Score、Test Trend）

## 工具與資源
- xUnit、FluentAssertions、NSubstitute/Moq、Bogus/AutoFixture
- Testcontainers、WireMock.Net、DotNet.Testcontainers
- Pact.NET、Playwright、Stryker.NET、Coverlet、ReportGenerator
