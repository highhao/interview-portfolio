# 技術作品集索引 | Project Portfolio

每個案例有獨立 GitHub 網址，方便依職務選擇連結。產險後端概觀與車險／旅平險 API 是同一產險服務模組的不同閱讀深度；其他案例各自分開整理。所有專案只放說明文件與圖表，不含原始程式碼。

## 產險後端

### 產險 SaaS 後端模組概觀
- **技術：** Java 11、Spring Boot 2.7.8
- **內容：** Controller、用例 Service、Worker、WebService、Repository／Mapper 的實際組織方式
- **專案：** [insurance-saas-platform](https://github.com/highhao/insurance-saas-platform)

### 車險與旅平險 API 分層案例
- **技術：** Java 11、Spring Boot 2.7.8
- **內容：** Controller DIO、用例 Service 繼承 BaseService、Worker 與直接 Mapper／Repository 依賴
- **專案：** [vehicle-travel-insurance-api](https://github.com/highhao/vehicle-travel-insurance-api)

## 其他後端專案

### 即時通訊與通知
- **技術：** Java、Spring
- **內容：** 訊息列表、未讀／已讀狀態與快取架構
- **專案：** [messaging-notification-platform](https://github.com/highhao/messaging-notification-platform)

### 翻譯 REST API
- **技術：** Java 11、Spring Boot 2.7.8
- **內容：** JWT、安全控制、資料存取與外部服務整合
- **專案：** [translation-api](https://github.com/highhao/translation-api)

## Web 應用

### Flask 電商網站
- **技術：** Python 3.11、Flask 3、MySQL
- **內容：** 商品、會員、Session 購物車與結帳資料流程
- **專案：** [flask-ecommerce](https://github.com/highhao/flask-ecommerce)

## 資料處理與同步

### 試算表專案追蹤同步
- **技術：** Google Sheets、Google Apps Script（JavaScript）
- **內容：** 員工分表、欄位級更新追蹤、主資料同步
- **專案：** [google-sheets-sync](https://github.com/highhao/google-sheets-sync)

### 酒類商品資料擷取
- **內容：** 靜態／動態來源抓取、抽象介面與共用商品資料格式
- **專案：** [alcohol-product-scraper](https://github.com/highhao/alcohol-product-scraper)

## 桌面端控制

### 桌面端控制與自動化平台
- **技術：** Vue 3、Java 21／Spring Boot 3.3.1、Java Windows Agent、Python 3.11+／FastAPI
- **內容：** Web UI 操作、Server 授權與任務政策、Agent 本機執行、Worker 擷取與分析
- **專案：** [desktop-control-platform](https://github.com/highhao/desktop-control-platform)
