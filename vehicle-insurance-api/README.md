# 車險與旅平險 API 結構

**開發內容：** 車險與旅平險 API。**語言與框架：** Java 17、Spring Boot 3.2.5。此案例聚焦 DIO/DTO、Controller、Service、Worker、Mapper/Repository 與 Entity 的程式結構，不呈現保險業務規則。

## 架構圖

![車險與旅平險 API 分層架構](docs/assets/architecture.svg)

## 模組分工

| 層級 | 程式結構 | 責任 |
|---|---|---|
| API 輸入 | Controller DIO | 承接 HTTP 請求資料，定義輸入契約 |
| API 輸出 | Controller DTO | 定義回應資料形狀，包含列表與分頁回應 |
| Controller | Spring REST Controller | 接收請求、驗證輸入、呼叫應用服務、封裝共用 Response |
| Service | `BaseService<DIO, Result>` 實作 | 組織處理步驟並產生標準回應 |
| Worker | Component / Worker | 封裝跨模組操作與資料存取協調 |
| Persistence | Mapper、Repository、Entity | 對應查詢、資料模型與儲存操作 |
| 外部 API | `RestWorker` + integration DIO | 封裝下游 HTTP 請求及其資料契約 |

## DIO 與 DTO 的界線

- **DIO** 在 Controller 層代表 API 輸入物件；在外部整合層也描述送往下游服務的請求資料。專案以套件位置區分用途。
- **DTO** 描述 API 回傳資料，可組合項目清單、分頁資訊及共用回應格式。
- **Entity/DO** 對應持久化模型；不直接等同於 API 輸入或回應契約。
- JSON 欄位名稱、序列化註記及 OpenAPI Schema 集中在資料物件上，讓 API 契約可被文件化。

## 設計模式與程式風格

- **Layered Architecture**：將 HTTP、應用處理、整合協調與持久化責任拆層。
- **Template Method**：Service 繼承共用 `BaseService`，透過 `processData` 與 `generateResult` 提供領域實作。
- **Repository / Data Mapper**：以 Repository 與 MyBatis Mapper 封裝資料存取方式。
- **Dependency Injection**：以 Spring 建構子注入明確表達元件依賴。
- **DTO boundary**：用獨立輸入／輸出型別隔離 API 契約、內部資料模型與下游服務契約。

English: Developed car and travel insurance APIs, with this case study focused on DIO/DTO contracts and layered Java/Spring design.
