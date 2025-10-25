# 事件驅動與訊息系統學習計畫

## 目標
- 理解事件驅動架構模式，掌握 Pub/Sub、CQRS、Saga 等設計
- 熟悉 RabbitMQ、Kafka、Azure Service Bus 等訊息中介的差異與操作
- 建立可靠傳遞、順序、重試、死信佇列等治理能力

## 核心主題
- 訊息模型：Command vs Event、At Most/Least/Exactly Once、Idempotency
- RabbitMQ（Exchange/Queue/Binding）、Kafka（Topic/Partition/Consumer Group）
- Outbox、Inbox、去重與補償交易（Saga / Process Manager）
- 監控與觀測：DLQ 分析、Lag Monitoring、Tracing（Activity/Span）

## 實作路線
1. 建立事件驅動範例：API 發佈事件 → Worker/Function 消費 → DB 更新
2. 實作 Outbox Pattern 與 Idempotent Consumer，驗證重放與重試策略
3. 比較 RabbitMQ 與 Kafka 的佈署、吞吐、順序特性，撰寫 Benchmark 報告
4. 串接 OpenTelemetry、Prometheus/Grafana 觀測訊息流動與 Lag

## 產出
- 事件驅動服務範例（RabbitMQ、Kafka 各一）
- Outbox/Inbox 套件或共用程式庫
- 訊息系統監控儀表板與治理手冊

## 工具與資源
- RabbitMQ、Kafka、Azure Service Bus、MassTransit、NServiceBus
- Debezium、Kafka Connect、Confluent Schema Registry
- OpenTelemetry、Prometheus、Grafana、Jaeger
