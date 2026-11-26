# 翻譯 API 請求處理流程

![請求處理流程圖](assets/workflow.svg)

Security Filter 驗證 token 並建立身份上下文，Controller 驗證 DTO 後呼叫 Service。Service 協調內部業務規則，依需求呼叫 Worker 或 Repository；共用例外處理與日誌提供一致的錯誤回應。
