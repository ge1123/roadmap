# Source Generators 與編譯期增強學習計畫

## 目標
- 理解 .NET Source Generators 運作機制與 Roslyn API
- 以編譯期自動化減少樣板程式、提升效能
- 確保產生碼的可測試性與診斷資訊完整

## 核心主題
- Roslyn 組件：Syntax API、Semantic Model、Incremental Generator
- 診斷與 Analyzer：`DiagnosticDescriptor`、Code Fix Provider
- 產生碼最佳化：增量生成、避免多餘 I/O、增量快取
- 實務案例：Settings 繫結、序列化 Context、API Client 代理、自動映射

## 實作路線
1. 建立 Incremental Generator，為 DTO 產生 `ToString`/Mapping 程式
2. 寫 Analyzer + Code Fix，強制 Domain 事件命名與結構規則
3. 透過 `Verify`/`Snapshot` 測試生成結果，並確保可在 CI 中運行
4. 評估與既有第三方 Generator（例如 `System.Text.Json` Source Generator）整合

## 產出
- Source Generator 專案範例（含 Analyzer/CodeFix）
- 生成碼的測試與診斷文檔
- 導入評估報告（效益、限制、維運建議）

## 工具與資源
- Roslyn SDK、Microsoft.CodeAnalysis 套件
- Uno.SourceGeneration、StrongInject、NetEscapades.Configuration
- Verify (snapshot testing)、RoslynQuoter、SharpLab
