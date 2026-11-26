# Personal Finance API

[繁體中文](./README.md) | **English** | [日本語](./README.ja.md)

A personal finance management RESTful API built with Java 21, Spring Boot 3, PostgreSQL, Docker Compose, JWT, and GitHub Actions CI.

> See the detailed API documentation in Swagger UI after starting the application.

## Quick start

```bash
# 1. Start the PostgreSQL container
docker compose up -d

# 2. Build and start the project (requires Java 21 and Maven locally)
cd personal-finance
mvn spring-boot:run

# 3. Open the Swagger documentation: http://localhost:8080/swagger-ui.html
```

## Project layout (database and temporary files omitted)

```text
personal-finance/
│   README.md                  # Project overview, installation, and usage documentation (Markdown)
│   pom.xml                    # Maven project dependencies and configuration
│   docker-compose.yml         # Docker Compose configuration for external services such as the database
│   .gitignore                 # Git ignore rules for temporary files and sensitive information
│
├───src
│   ├───main
│   │   ├───java
│   │   │   └───com
│   │   │       └───example
│   │   │           └───personalfinance
│   │   │               ├───controller    # API controllers: HTTP request entry points
│   │   │               ├───service       # Business logic and data processing
│   │   │               ├───repository    # Data access through JPA and the database
│   │   │               ├───domain        # Data models (entities and enums)
│   │   │               ├───dto           # Request and response formats (data transfer objects)
│   │   │               ├───security      # JWT and Spring Security authentication and authorization
│   │   │               └───exception     # Global exception handling and standardized error messages
│   │   └───resources
│   │        application.yml  # Spring Boot configuration (database connection, JPA, etc.)
│   └───test
│        └───java
│             └───com
│                 └───example
│                      └───personalfinance
│                         # Unit and integration tests
├───.github
│   └───workflows
│        ci.yml            # GitHub Actions configuration for automated CI
```
