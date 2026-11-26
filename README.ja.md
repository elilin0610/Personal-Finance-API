# Personal Finance API

[繁體中文](./README.md) | [English](./README.en.md) | **日本語**

Java 21、Spring Boot 3、PostgreSQL、Docker Compose、JWT、GitHub Actions CI を使用した、個人向け家計管理用の RESTful API です。

> 起動後、Swagger UI で API の詳細を確認できます。

## クイックスタート

```bash
# 1. PostgreSQL コンテナーを起動する
docker compose up -d

# 2. ビルドして起動する（ローカルに Java 21 と Maven が必要）
cd personal-finance
mvn spring-boot:run

# 3. Swagger のドキュメントを開く: http://localhost:8080/swagger-ui.html
```

## ディレクトリ構成（データベースと一時ファイルを除く）

```text
personal-finance/
│   README.md                  # プロジェクト概要、インストール、使い方（Markdown）
│   pom.xml                    # Maven の依存関係と設定
│   docker-compose.yml         # データベースなど外部サービスの Docker Compose 設定
│   .gitignore                 # 一時ファイルや機密情報を除外する Git 設定
│
├───src
│   ├───main
│   │   ├───java
│   │   │   └───com
│   │   │       └───example
│   │   │           └───personalfinance
│   │   │               ├───controller    # API コントローラー。HTTP リクエストの入口
│   │   │               ├───service       # ビジネスロジックとデータ処理
│   │   │               ├───repository    # JPA とデータベースを接続するデータアクセス層
│   │   │               ├───domain        # データモデル（エンティティと列挙型）
│   │   │               ├───dto           # リクエストとレスポンスの形式（DTO）
│   │   │               ├───security      # JWT と Spring Security による認証・認可
│   │   │               └───exception     # 共通の例外処理とエラーメッセージの標準化
│   │   └───resources
│   │        application.yml  # Spring Boot 設定（データベース接続、JPA など）
│   └───test
│        └───java
│             └───com
│                 └───example
│                      └───personalfinance
│                         # ユニットテストと結合テスト
├───.github
│   └───workflows
│        ci.yml            # CI を自動実行する GitHub Actions 設定
```
