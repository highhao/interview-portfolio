# SaaS API 請求流程

![平台 API 請求流程圖](assets/workflow.svg)

API 請求先經身份驗證及權限檢查，再由 Controller 驗證輸入並交給 Service 執行領域規則。Service 協調資料讀寫和必要的外部服務呼叫，最後回傳統一格式的結果。統一錯誤處理、API 日誌及監控支援故障追蹤。
