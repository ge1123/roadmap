# 事件儲存與資料管線學習計畫

## 目標
- 掌握 Event Sourcing、CQRS 與資料管線設計，因應審計與回放需求
- 熟悉資料流分層：Raw → Cleansed → Curated，並維持一致性
- 介紹流式處理、批次處理與 CDC（Change Data Capture）整合

## 核心主題
- Event Store 模型設計：Aggregate Stream、Snapshot、Schema 演進
- Command Handler → Event Store → Projection → Read Model 流程
- 資料管線工具：Azure Data Factory、AWS Glue、Debezium、Kafka Streams
- 資料品質治理（DQ Checks、Schema Registry）、追蹤與重放策略

## 實作路線
1. 使用 EventStoreDB 或 Marten 實作 Order/Payment 聚合的事件儲存
2. 建立 Projections，透過 Background Worker/Projection Daemon 更新讀模型
3. 整合 CDC（Debezium）將變更送入 Kafka，再流向清洗/分析層
4. 撰寫回放與快照策略，模擬事件演進（Schema Change）流程

## 產出
- Event Sourcing 範例專案（包含 Snapshot、Projection、重放腳本）
- 資料管線設計文件（Raw → Clean → Serve）的步驟與 SLA
- 監控儀表板（處理延遲、投影狀態、錯誤重試）

## 工具與資源
- EventStoreDB、Marten、NEventStore、MassTransit Saga
- Debezium、Kafka Connect、Azure Data Factory、AWS Glue
- dbt、Apache Beam、Flink、Lakehouse（Delta、Iceberg）
