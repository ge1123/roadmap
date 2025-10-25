# 分散式快取學習計畫

[待辦事項](../todo/distributed_cache_plan.md)

## 目標
- 了解快取模式、分散式一致性與資料失效策略
- 在 .NET 中建構高效、可觀測的快取層，支援高併發與容錯
- 評估各類快取技術（Redis、Memcached、Hazelcast）與雲端託管方案

## 核心主題
- 快取模式：Cache-Aside、Write-Through、Write-Behind、Read-Through
- Key 設計、TTL、LRU/LFU、分片/叢集、資料一致性與雪崩防護
- Redis 功能：Hash、Sorted Set、Streams、Pub/Sub、Lua Script、Geo
- 快取治理：Metrics、慢查詢、熱點緩解、資料預熱、版本管理

## 實作路線
1. 導入 StackExchange.Redis，封裝快取服務 + 指標（命中率、延遲）
2. 實作 Cache Aside 與 Write Behind，並測試多節點故障恢復
3. 建立快取一致性策略：分布式鎖、版本標記、事件驅動失效
4. 評估 Redis Cluster/Azure Cache/AWS Elasticache 的部署與監控

## 產出
- 快取策略文件與治理手冊
- 快取封裝程式庫（含觀測與測試）
- 壓測報告（命中率、延遲、資源使用）

## 工具與資源
- StackExchange.Redis、Microsoft.Extensions.Caching.StackExchangeRedis
- RedisInsight、Azure Cache for Redis、AWS ElastiCache
- k6、Bombardier、Grafana、Prometheus、Redis Exporter
