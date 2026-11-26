# Shopping Website

Flask 電商網站，提供商品瀏覽、會員驗證、購物車與結帳流程，並整合 MySQL、OAuth、SMTP、Socket.IO 及 ECPay 模組。

## 架構與流程

應用程式工廠集中載入設定與註冊功能 Blueprint。路由按商品、會員、購物車及付款等職責拆分；資料經 MySQL 存取，頁面使用 Jinja2 呈現。

- [系統架構](docs/architecture.md)
- [購物與結帳流程](docs/workflow.md)

## 工程規劃

- 以功能模組組織路由，讓業務入口容易定位。
- 讓頁面模板與 JSON API 支援不同前端互動方式。
- 後續可將商業規則與 SQL 存取分別抽到 Service、Repository，提升測試性。
- 結帳流程應以資料庫交易保障訂單與庫存一致，付款通知需驗簽並冪等處理。

English: A Flask e-commerce application with product browsing, session cart, authentication, and payment integration components.
