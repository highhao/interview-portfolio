# Flask 電商網站

Flask 電商網站，提供商品瀏覽、會員驗證、購物車與結帳頁面，並整合 MySQL、OAuth、SMTP、Socket.IO 及 ECPay 模組。

## 技術組成

- Python 3.11、Flask 3、MySQL
- Jinja2、HTML、CSS、JavaScript、MDB/Bootstrap
- Flask-SocketIO、OAuth、SMTP、ECPay
- Docker、Gunicorn

## 架構與流程

應用程式工廠載入設定並註冊功能 Blueprint。路由依商品、會員、購物車與付款等功能拆分；資料由 MySQL 存取，頁面以 Jinja2 呈現。

- [系統架構](docs/architecture.md)
- [購物與結帳流程](docs/workflow.md)

English: A Flask e-commerce application with product browsing, session cart, authentication, and payment integration components.
