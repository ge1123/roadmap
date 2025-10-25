# 設計模式核心學習計畫

[待辦事項](../todo/design_patterns_plan.md)

## 目標
- 強化面向物件設計能力，提升程式可維護性與擴充性
- 在 .NET 生態中理解模式與框架實踐（ASP.NET Core、EF Core 等）
- 以實務案例串接模式組合（例如 DDD、事件驅動架構）

## 核心主題
- SOLID 原則、Clean Code、Refactoring 手法
- 經典 GoF 模式：建立、結構、行為（Factory、Strategy、Composite、Decorator、Observer 等）
- CQRS、MediatR、Specification、Pipeline 行為模式
- Anti-patterns 與設計味道（Shotgun Surgery、God Object、Anemic Domain Model）

## 實作路線
1. 針對既有專案重構：套用 Dependency Inversion、門面/適配器模式
2. 以 MediatR 實作 CQRS + Pipeline Behaviors（Logging、Validation、Caching）
3. 建立範例專案展示策略模式 + 組合 + Decorator 的整合應用
4. 撰寫設計決策記錄（ADR），記錄模式選擇與權衡

## 產出
- 設計模式實戰範例庫（含測試）
- Refactoring 前後比較說明與維護性分析
- ADR 與設計準則清單

## 工具與資源
- Refactoring Guru、Head First Design Patterns、Pattern-Oriented Software Architecture
- ReSharper / Rider Inspect Code、SonarQube
- MediatR、Scrutor、FluentValidation
