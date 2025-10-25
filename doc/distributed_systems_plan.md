# 分散式系統與 Kubernetes 學習計畫

## 目標
- 建立分散式系統設計思維：一致性、可用性、可觀測性、彈性伸縮
- 熟悉容器化與 Kubernetes 基礎，能操作部署、監控、調試
- 整合雲端服務、Service Mesh、GitOps 等現代運維模式

## 核心主題
- CAP、PACELC、12-Factor、Sidecar 與 Service Mesh 模式
- 容器化基礎：Dockerfile、映像最佳化、多階段建置
- Kubernetes 基礎元件：Pod、Deployment、Service、Ingress、ConfigMap、Secret
- 可觀測性：Prometheus、Grafana、Jaeger、OpenTelemetry Collector
- GitOps 與宣告式部署：Argo CD、Flux

## 實作路線
1. 將 .NET 服務容器化，設計健康檢查、資源限制、環境設定
2. 建立本地 K8s（kind/minikube）部署範例，導入 HPA、PodDisruptionBudget
3. 整合 Service Mesh（Istio/Linkerd），實驗金絲雀流量拆分與 mTLS
4. 建置 GitOps Pipeline（Argo CD）與監控儀表板、Logging Stack（EFK/ELK）

## 產出
- Kubernetes 部署清單與模板（Helm/Kustomize）
- GitOps 流程範例與操作手冊
- 監控/Tracing Dashboard 與異常排查案例

## 工具與資源
- Docker、containerd、kind、minikube、k3d
- Helm、Kustomize、Argo CD、Flux
- Prometheus、Grafana、Loki、Jaeger、OpenTelemetry Collector
