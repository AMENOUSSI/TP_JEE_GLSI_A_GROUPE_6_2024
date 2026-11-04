# Bank Account Management

A Java/Spring Boot application for managing banking clients, accounts, and transactions. The project includes REST controllers, persistence with Spring Data JPA, and MySQL integration. Account types include current accounts and savings accounts.

## Tech stack

- Java 17
- Spring Boot 3.2.1
- Spring Web and Spring Data REST
- Spring Data JPA / Hibernate
- MySQL
- Maven (Maven Wrapper included)

## Requirements

- JDK 17 or later
- MySQL server

## Setup

1. Clone the repository and move into the project directory:

   ```bash
   git clone https://github.com/AMENOUSSI/TP_JEE_GLSI_A_GROUPE_6_2024.git
   cd TP_JEE_GLSI_A_GROUPE_6_2024
   ```

2. Create a MySQL user and configure the database connection in `src/main/resources/application.properties`. The current configuration targets a local MySQL database named `banke` on port `3306`; update the URL, username, and password for your environment. Do not commit real credentials.

3. Start the application with the Maven Wrapper:

   ```bash
   # macOS / Linux
   ./mvnw spring-boot:run

   # Windows
   mvnw.cmd spring-boot:run
   ```

   The application is configured to listen on port `8084`.

## Build and tests

```bash
./mvnw clean package
./mvnw test
```

On Windows, use `mvnw.cmd` instead of `./mvnw`.

## Project layout

```text
src/
├── main/java/glsia6/com/compteManagement/
│   ├── config/       # Application configuration
│   ├── controller/   # REST controllers
│   ├── dto/          # Data transfer objects
│   ├── entity/       # Client, account, and transaction entities
│   ├── repository/   # Persistence repositories
│   ├── service/      # Service interfaces
│   └── serviceImpl/  # Service implementations
└── main/resources/   # Spring configuration
```

## Database note

The checked-in configuration currently uses `spring.jpa.hibernate.ddl-auto=create`, which recreates the schema at startup and can erase existing data. Change this setting to an appropriate value for your environment (for example, `update` for local development) before running against data you need to keep.
