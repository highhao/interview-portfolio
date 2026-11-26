# 酒類商品資料擷取案例

專案工作情境為從五個網站擷取酒類商品資訊。面試說明聚焦多來源資料擷取的架構分工：來源設定、各來源擷取器、共同輸出邊界，以及錯誤記錄與資料品質檢視。

![多來源資料擷取流程圖](docs/assets/workflow.svg)

## 架構與設計重點

- 每個網站的差異由來源專屬擷取步驟承接，避免網站結構差異散落在共用流程。
- 共用流程負責排程／執行協調、結果彙整與錯誤觀測。
- 輸出欄位應有明確契約，便於後續匯入、查詢或分析。
- 多來源資料品質需考慮缺漏欄位、格式差異與重複項目。

English: A multi-source data collection case focused on separating source-specific extraction from shared orchestration and output contracts.
