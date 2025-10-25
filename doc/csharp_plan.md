# C# / .NET 深度讀書計畫

> 適用背景：曾開發 .NET 6 的工程師，聚焦 ASP.NET Core 內部機制、必備套件與現代化平台能力  
> 目標：掌握語言演進 → 平台機制（Middleware、Filter、Attribute、DI、Hosting）→ 資料與訊息 → 整體架構與部署

[待辦事項](../todo/csharp_plan.md)

## 階段 1｜語言、異步與效能基礎
- **掌握重點**：`required`、Primary Constructors、Records、`switch` expression、`with`、`Span<T>`/`Memory<T>`、`ValueTask`
- **實作練習**：
  - 撰寫 10 個 LINQ Kata（含投影、分組、Join、Window）
  - BenchmarkDotNet 對比 `string` 拼接 vs `StringBuilder`、`Substring` vs `Span<T>`
- **產出**：`語法速查筆記.md`、Benchmark 報告
- **工具提示**：BenchmarkDotNet、dotnet-counters、dotnet-trace

## 階段 2｜ASP.NET Core 請求管線與核心機制
- **掌握重點**：
  - Hosting 模型（Generic Host、WebApplicationBuilder）、環境與設定載入流程
  - Middleware pipeline 設計：自訂 Middleware、Pipeline Branch、UseWhen、短路與 Exception Handling
  - Routing/Endpoint、Filters（Resource/Action/Exception）、Attribute 驅動行為（`[From*]`、`[ApiController]`、自訂 Attribute）
  - 內建 DI Container 與進階註冊模式（Scoped/Lifetime、Options、IServiceProviderFactory）
  - Configuration/Options、Logging/Serilog、ProblemDetails 與統一錯誤處理
- **實作練習**：
  - 建立可切換 Minimal API / Controller 的樣板，展示 Middleware/Filter/Attribute 責任分工
  - 自訂 Middleware（Correlation Id、Request Logging）、Action Filter（Validation、Audit）與 Endpoint Filter
  - 探索依賴注入：Factory、Decorator、Scrutor 批次註冊，撰寫 Integration Test 驗證
- **產出**：Clean API Template、請求管線圖、DI 註冊指南
- **工具提示**：ASP.NET Core Diagnostics、Serilog、Scrutor、MiniProfiler

## 階段 3｜資料存取策略與常用套件
- **掌握重點**：
  - EF Core 9：Migrations、`AsNoTracking`、批次 Save、`RowVersion`、Value Converter、Global Query Filter
  - Dapper：高頻查詢、TVP、動態 SQL、`SqlMapper` 擴充、Result Cache
  - 驗證與 Mapping：FluentValidation、AutoMapper/Mapster
  - 擴充套件：MediatR（CQRS/Pipeline Behaviors）、Polly（重試、斷路器）、Serilog Sink
- **實作練習**：
  - 建立雙 Repository 範例：EF Core 處理交易邏輯、Dapper 處理查詢
  - 以 MediatR Pipeline 集中日誌、驗證、快取；整合 FluentValidation 作請求驗證
  - BenchmarkDotNet 比較 EF vs Dapper 的查詢/寫入效能，分析交易/連線池設定
- **產出**：DB Schema SQL、Repository/Query 樣板、MediatR Pipeline 說明
- **工具提示**：EF Core CLI、Dapper、FluentValidation、MediatR、Polly、AutoMapper/Mapster

## 階段 4｜事件驅動、背景工作與觀測性整合
- **掌握重點**：Worker Service、Hangfire/Quartz 排程重試、死信監控、Channel 背景處理
- **Pipeline 機制**：MediatR Command/Query、Notification、Pipeline Behaviors；自訂 Attribute 控制快取/授權
- **觀測性**：OpenTelemetry Tracing/Metrics、健康檢查、Serilog Enricher
- **實作練習**：
  - 建置 `src/Worker` 監控檔案來源（目錄或 S3），支援重試、死信
  - API → MediatR → Worker 任務串聯，使用 Outbox/Inbox 確保一致性
  - 透過 OpenTelemetry + Jaeger/Grafana 建立事件流水追蹤
- **產出**：API + Worker 串流流程、Tracing 視覺化、MediatR 行為庫
- **工具提示**：Hangfire/Quartz.NET、Worker Service、OpenTelemetry (OTLP)、Grafana Tempo/Prometheus、Serilog、MediatR.Extensions

## 階段 5｜端到端 ETL 微服務（Capstone）
- **掌握重點**：CSV 上傳、Schema 驗證、清洗規則、批次入庫、交易/重試、通知、觀測性
- **實作練習**：
  - `POST /imports` 建立匯入任務（回傳 JobId），Worker 佇列消費
  - 實作清洗流程（時區、空值、Regex），寫入 `JobLog`／`UploadFileLog`
  - 建立查詢 API（依日期/狀態/來源檔），以 Attribute/Filters 控制授權、快取、節流
- **產出**：可執行的 ETL 微服務（API + Worker + DB + Metrics）
- **工具提示**：Serilog RequestLogging、Polly 重試、Email/Webhook 通知整合、MediatR、FluentValidation、EF Core、Dapper

## 階段 6｜效能優化、Native AOT 與雲端部署
- **掌握重點**：Native AOT Trim、Reflection 白名單、容器最佳化、多階段 Docker、GitHub Actions、雲端部署策略
- **實作練習**：
  - Worker 使用 Native AOT，API 切換 Self-contained/Framework-dependent
  - 建置 CI/CD（Build、測試、掃描、推送），撰寫 Dockerfile 與健康檢查
  - 使用 Bombardier/k6 壓測，透過 OpenTelemetry + Grafana 觀測 RPS/P95
  - 部署至 AWS ECS/Fargate 或 Azure Container Apps，配置 Auto Scaling、Secrets 管理
- **產出**：容器化部署版本、壓測報告與指標分析
- **工具提示**：Docker、多階段建置、GitHub Actions、AWS CDK/Terraform、Azure Bicep

## Side Project 建議（擇二）
- 檔案上傳校驗服務：支援 CSV/Excel、欄位映射、錯誤報表導出
- 事件驅動清洗管線：API 發佈事件 → Worker 消費 → SQL 落地
- 規則引擎微服務：策略模式 + 規則資料表，支援熱更新

## 必備套件與框架清單
- **框架機制**：ASP.NET Core Middleware、Endpoint/Filter、Attribute、DI Container、Options、ProblemDetails
- **資料層**：Entity Framework Core、Dapper、DbUp
- **CQRS / Mediator**：MediatR、MediatR.Extensions.Microsoft.DependencyInjection
- **驗證與行為**：FluentValidation、AutoMapper/Mapster、Scrutor
- **觀測性與可靠性**：Serilog、Seq、OpenTelemetry、Polly、HealthChecks、MiniProfiler
- **背景工作與排程**：Hangfire、Quartz.NET、Worker Service
- **測試支援**：xUnit、FluentAssertions、Testcontainers、Respawn

## 進階延伸主題
- gRPC / SignalR 即時通訊
- Source Generators、自動程式碼產生
- 分散式快取：Redis + StackExchange.Redis
- 安全與驗證：JWT、Key rotation、最小權限、OWASP Top 10
- 序列化優化：`System.Text.Json` 原位寫入、`JsonSerializerContext`
- 效能心法：分批寫入、`SqlBulkCopy`、連線池管理、`IAsyncEnumerable<T>` 流式處理
