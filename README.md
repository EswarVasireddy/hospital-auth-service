# Hospital Auth Service

A Spring Boot backend service that provides JWT-based user authentication for a hospital management system.

## Features

- User signup and login
- Password-protected user accounts (MySQL-backed via Spring Data JPA)
- JWT token generation for authenticated sessions
- Spring Security configuration for route protection
- Dockerized for easy deployment

## Tech Stack

- **Language / Framework:** Java, Spring Boot 3.4
- **Security:** Spring Security, JJWT (JSON Web Tokens)
- **Persistence:** Spring Data JPA, MySQL
- **Build tool:** Maven
- **Containerization:** Docker

## Project Structure

```
src/main/java/com/klu/hospital/
├── HospitalApplication.java      # Application entry point
├── controller/
│   └── AuthController.java       # /auth/signup and /auth/login endpoints
├── entity/
│   └── User.java                 # User entity (id, username, email, password)
├── repository/
│   └── UserRepository.java       # Spring Data JPA repository
├── security/
│   ├── JwtUtil.java               # JWT generation/validation
│   ├── SecurityConfig.java        # Spring Security configuration
│   └── UserDetailsServiceImpl.java
└── service/
    └── UserService.java          # Registration & login business logic
```

## API Endpoints

| Method | Endpoint        | Description                        |
|--------|-----------------|-------------------------------------|
| POST   | `/auth/signup`  | Register a new user (`username`, `email`, `password`) |
| POST   | `/auth/login`   | Authenticate a user and return a result (`username`, `password`) |

## Getting Started

### Prerequisites

- Java 17+
- Maven (or use the included `mvnw` wrapper)
- MySQL running locally (update credentials in `application.properties`)

### Run locally

```bash
./mvnw spring-boot:run
```

### Run with Docker

```bash
docker build -t hospital-auth-service .
docker run -p 8080:8080 hospital-auth-service
```

## Status

This is the authentication module of a larger hospital management system. See the [hospital-management-system](https://github.com/EswarVasireddy/hospital-management-system) repo for the full frontend + backend application.
