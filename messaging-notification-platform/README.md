# 即時通訊與通知

負責即時訊息與通知系統的程式開發。文件整理會話列表、未讀／已讀狀態、置頂及快取相關架構。

## 架構

前端透過 API 讀取列表或更新訊息狀態。Controller 接收請求，Application Service 協調訊息、通知與會話規則，Repository 封裝資料操作；狀態更新後清除相關列表快取。

[架構與狀態流程](docs/architecture.md)

## 設計重點

- **以畫面邏輯項目聚合資料**：將通知類別、私聊對象及群聊會話整理成一致的列表項目。
- **集中狀態規則**：未讀數、最後訊息、已讀游標、置頂與靜音由服務層協調。
- **明確分層**：Service 不直接跨模組操作資料 Mapper，透過 Repository 收斂查詢責任。
- **使用明確型別表達狀態**：以 enum 取代散落的字串或數字狀態，減少錯誤組合。
- **快取處理**：訊息送達或標記已讀後，使相關列表快取失效。

English: A messaging system focused on aggregated conversation lists and consistent unread/read state management.
