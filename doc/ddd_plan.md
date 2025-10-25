# Domain-Driven Design 學習計畫

## 目標
- 掌握 DDD 核心概念，能以通用語言與業務共創模型
- 建立限界上下文、聚合與領域事件的實作能力
- 將 DDD 與 Clean Architecture、微服務、事件驅動等主題串連

## 核心主題
- 戰術設計：Entity、Value Object、Aggregate、Domain Service、領域事件
- 策略設計：限界上下文、Context Mapping、通用語言、Core/Supporting/Generic Domain
- 模型持續演化：事件風暴、聚合切分、交易一致性策略
- Anti-Corruption Layer、Integration Patterns、讀寫模型分離

## 實作路線
1. 針對既有業務流程進行事件風暴，產出 Domain Story 與 Context Map
2. 建立聚合根與 Value Object，實作不變條件與領域事件
3. 透過 Application Layer + MediatR 暴露 CQRS 介面，搭配持久層策略
4. 整合事件驅動（Outbox、Message Relay），確保跨 Context 一致性

## 產出
- DDD 藍圖：Context Map、聚合設計、Ubiquitous Language 清單
- 範例解決方案（API + Domain + Infrastructure）與測試
- DDD 實施指南（組織推動、常見陷阱）

## 工具與資源
- Domain-Driven Design Distilled、Implementing Domain-Driven Design
- EventStorming Guide by Alberto Brandolini
- MediatR、Automatonymous、MassTransit、Entity Framework Core
