# 產險 SaaS 後端平台

Java 17、Spring Boot 3.2.5 後端服務，作為產險 SaaS 平台的 API 與整合層。程式碼呈現多個服務領域 API、身份與權限驗證、資料存取、即時通訊、排程及雲端服務整合。

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

程式目錄可辨識 app、driving、rentDriver、rentStore 等 API 領域。這些是平台內的服務模組；此案例以產險 SaaS 後端平台為整體情境，不將特定公司或客戶名稱放入作品集。

## API 處理流程

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

- 以領域目錄組織 API、DTO 與服務，降低不同業務流程互相干擾。
- Controller 保持薄層，將主要規則交由 Service；外部 API 呼叫隔離在 Worker。
- 使用輸入驗證、共用錯誤類型及標準 Response，讓 API 行為更一致。
- 資料存取同時使用 JPA、JDBC 與 MyBatis；明確界定各技術的使用情境，可避免重複抽象並提高維護性。
- 可持續改善的方向包括外部呼叫 timeout/retry、交易邊界、測試隔離與敏感資料日誌遮罩。

English: A Java 17 / Spring Boot backend for an insurance SaaS platform, organized into API, security, domain, persistence, and integration layers.
