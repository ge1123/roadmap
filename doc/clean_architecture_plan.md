# Clean Architecture 與微服務學習計畫

## 目標
- 建立分層、依賴反轉與界面隔離的實作能力
- 將微服務與 Clean Architecture 結合，掌握界面、資料、部署邊界
- 強化可持續交付、可測試、可觀測的系統設計

## 核心主題
- Clean Architecture 圖層：Domain、Application、Infrastructure、Presentation
- 模組邊界與封裝、組件級依賴管理（NuGet/Project references）
- 微服務切分準則：業務能力、交易邊界、資料一致性與 API 合約
- API Gateway、BFF、Service Mesh、Cross-Cutting Concern（觀測、驗證、授權）

## 實作路線
1. 以現代模板（Minimal API + MediatR + EF + Infrastructure）建立範例專案
2. 定義模組契約與 DTO 映射，導入依賴反轉與策略註冊（Scrutor）
3. 將單體拆分為數個邏輯服務，設計 API Gateway / BFF 與共享契約
4. 導入觀測性（OpenTelemetry）、集中式設定、健康檢查與回復策略

## 產出
- Clean Architecture 樣板專案（含測試與 CI Pipeline）
- 微服務切分決策記錄與部署拓樸圖
- 服務對服務契約（API/事件）與錯誤處理指南

## 工具與資源
- `.NET` 官方模板、Jason Taylor Clean Architecture 範例
- YARP、Ocelot、Envoy、Istio（Service Mesh）
- OpenTelemetry、Serilog、FluentValidation、Polly
