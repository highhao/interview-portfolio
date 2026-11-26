# 翻譯 API

以 **Java 11、Spring Boot 2.7.8** 建置的 REST API，採 Controller、Service、Repository/DAO 與 Worker 分層，整合 JWT、安全控制、PostgreSQL 及外部 REST 服務。

- [系統架構](docs/architecture.md)
- [請求流程](docs/workflow.md)

## 工程設計

- Controller 管理 HTTP 契約與 request/response DTO。
- Service 協調業務流程，Repository/DAO 封裝資料存取。
- Worker 隔離認證、SSO 與外部 REST 呼叫。
- Security Filter 負責身份與權限處理；程式中另有共用例外、回應 DTO 與日誌元件。

English: A Java 11 / Spring Boot 2.7 REST API with layered services, JWT security, PostgreSQL, and external integrations.
