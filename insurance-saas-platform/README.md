# 產險 SaaS 後端平台

Java 17、Spring Boot 3.2.5 產險 SaaS 後端服務。**負責車險與旅平險 API 開發**；程式以 Controller、Service、Worker、資料存取與外部整合分層，支援平台 API 與服務整合。

## 技術組成

| 類別 | 技術 |
|---|---|
| 語言與框架 | Java 17、Spring Boot 3.2.5、Spring Web、Spring Security |
| API 與驗證 | REST、Bean Validation、JWT、OpenAPI/Swagger |
| 資料存取 | PostgreSQL、Spring Data JPA/JDBC、MyBatis |
| 非同步與即時 | Spring Batch、Scheduling、WebSocket |
| 雲端整合 | Firebase Admin、Google Cloud Storage |
| 建置與交付 | Maven、GitLab CI、Cloud Build/Deploy |

## 架構

![產險 SaaS 平台架構圖](docs/assets/architecture.svg)

平台以 REST API 作為服務入口，Controller 驗證請求並轉換 DTO；Security Filter 建立身份上下文；Service 協調領域規則，透過資料存取層與外部整合 Worker 存取資料及雲端服務。共用錯誤、日誌、監控與 API 文件支援跨模組一致性。

## API 請求流程

![SaaS API 請求流程圖](docs/assets/workflow.svg)

## 架構與設計模式

| 設計 | 程式中的呈現 | 解決的問題 |
|---|---|---|
| 分層架構 | Controller、Service、DAO/Repository、Worker | 分離 API、業務、資料與外部整合責任 |
| DTO | 各 API 的 request/response DTO | 隔離外部 API 契約與內部資料模型 |
| Repository | 資料存取介面與 Entity | 集中資料讀寫，降低服務直接依賴資料細節 |
| Dependency Injection | Spring 建構子注入與 Bean | 明確依賴並提升模組替換與測試能力 |
| Security Filter Chain | JWT 與 Spring Security Filter | 將身份驗證、權限檢查置於業務處理之前 |
| Worker / Adapter boundary | 外部 Auth、SSO、Cloud、REST 呼叫 | 封裝外部服務協定與依賴 |

## 程式規劃與 Clean Code

- 以業務領域組織 Controller、DTO 與 Service，降低功能交錯。
- 使用 DTO 作為 API 契約，並以 Bean Validation 驗證請求。
- 透過依賴注入連接服務層與資料／外部整合層，避免 Controller 承擔資料處理細節。
- 資料依賴同時包含 JPA、JDBC 與 MyBatis；明確界定各技術的使用情境，可避免重複抽象並提高維護性。
- 可持續改善的方向包括外部呼叫 timeout/retry、交易邊界、測試隔離與敏感資料日誌遮罩。

English: Developed car and travel insurance APIs in a Java 17 / Spring Boot SaaS backend, using layered API, persistence, security, and integration components.
