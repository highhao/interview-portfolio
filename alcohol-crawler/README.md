# 酒類資料擷取案例

以自動化方式擷取五個網站的酒類商品資料。現有可辨識素材提供了工作情境及操作示範，可將面試說明聚焦於多來源資料擷取、欄位正規化與資料品質管理。

![資料流程概觀](docs/assets/workflow.svg)

## 資料流程

不同網站的商品頁面先由來源專屬擷取步驟取得，再轉換為共同欄位格式；整理後的資料可供後續查詢或分析。多來源設計的關鍵在於欄位映射、缺漏值處理、重複資料判定、來源差異及失敗重試。

目前可檢視素材沒有提供程式碼，因此語言、爬取工具、儲存方式與排程方式不列入技術清單。

English: A multi-source product data collection task covering five websites, with emphasis on normalization and data quality.
