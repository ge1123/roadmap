# 前端整合學習計畫（Razor、React）

## 目標
- 理解 .NET 伺服端渲染與現代 SPA 的整合策略
- 建立一致的設計系統、認證流程與 API 合約
- 熟悉前後端協作、BFF、部署與效能優化

## 核心主題
- Razor Pages / MVC vs Blazor / React 差異與適用情境
- 前後端分離與 BFF 模式（YARP、Node.js、Azure Functions）
- 身分驗證與授權：OpenID Connect、OAuth 2.0、Cookie vs Token
- API 合約治理與型別共享（NSwag、OpenAPI、TypeScript SDK）
- 前端性能：Bundling、SSR/SSG、Code Splitting、懶載入

## 實作路線
1. 建立 Razor MVC + React SPA 的混合專案，共用身份驗證與授權機制
2. 透過 BFF (YARP/Minimal API) 統一 API 呼叫與快取，實作 CSRF/Token Refresh
3. 自動生成前端型別與 Client（NSwag、openapi-typescript-codegen）
4. 針對前端部署（Vite/Next.js）與 CDN 線路配置，加入端到端監測（App Insights）

## 產出
- 前後端整合範例專案（含 Auth、API SDK、CI/CD）
- 設計系統與共用元件庫（Storybook、Tailwind/Bootstrap）
- 前端性能與可用性報告（Lighthouse、Web Vitals）

## 工具與資源
- ASP.NET Core Razor Pages、Blazor、React、Next.js、Vite
- TypeScript、React Query、Redux Toolkit / Zustand
- YARP、NSwag、Swashbuckle、Azure Static Web Apps、Netlify、Vercel
