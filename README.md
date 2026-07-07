# Personal Finance API

A personal finance management RESTful API built with Java 21, Spring Boot 3, PostgreSQL, Docker Compose, JWT, and GitHub Actions CI.

> See detailed API documentation in Swagger UI once running.

## Quick Start

```bash
# 1. 啟動 Postgres 容器
docker compose up -d

# 2. 編譯並啟動專案（本地需安裝 Java 21 & Maven）
cd personal-finance
mvn spring-boot:run

# 3. 瀏覽 Swagger 文件: http://localhost:8080/swagger-ui.html
```

## 專案目錄結構（不含 DB 及暫存檔）

personal-finance/
│   README.md                  # 專案介紹文件 (Markdown 格式，推薦寫專案說明/安裝/使用方式)
│   pom.xml                    # Maven 專案依賴/設定檔
│   docker-compose.yml         # Docker Compose 設定（定義DB等外部服務）
│   .gitignore                 # Git 忽略規則，避免暫存檔、敏感資料入庫
│
├───src
│   ├───main
│   │   ├───java
│   │   │   └───com
│   │   │       └───example
│   │   │           └───personalfinance
│   │   │               ├───controller    # API controller，處理 HTTP 請求進入點
│   │   │               ├───service       # 業務邏輯層，封裝運算/資料處理
│   │   │               ├───repository    # 資料存取層，連接 JPA 與 DB
│   │   │               ├───domain        # 資料模型（Entity、Enum）
│   │   │               ├───dto           # 輸入/輸出資料格式 (Data Transfer Object)
│   │   │               ├───security      # JWT、Spring Security 認證/權限模組
│   │   │               └───exception     # 全域例外處理、錯誤訊息標準化
│   │   └───resources
│   │        application.yml  # Spring Boot 設定檔（DB連線、JPA等）
│   └───test
│        └───java
│             └───com
│                 └───example
│                      └───personalfinance
│                         # 單元/整合測試程式
├───.github
│   └───workflows
│        ci.yml            # GitHub Actions 設定檔，自動執行CI流程