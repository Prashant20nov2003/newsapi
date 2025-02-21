# News API Server - A Sample Go REST API

This project demonstrates the development of a RESTful API service using the Go programming language. It aims to provide a solid foundation for building your own APIs, adhering to common patterns and conventions.

![Go Version](https://img.shields.io/badge/Go-1.x+-00ADD8?style=flat&logo=go)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## Features

* RESTful API design following best practices (GET, POST, PUT, DELETE for CRUD operations)
* Modular code structure with clear separation of concerns (handlers, models, database access, etc.)
* PostgreSQL database integration for persistent storage
* Structured logging for better debugging and monitoring
* Built-in unit tests for core functionalities
* Database migration system

## Project Structure

```
├── cmd/
│   ├── api-server/     # Main application entry point
│   └── migrate/        # Database migration tool
├── deployment/         # Deployment configurations and Docker files
└── internal/
    ├── handler/        # API request handlers
    │   └── mocks/      # Mock implementations for testing
    ├── logger/         # Structured logging implementation
    ├── migration/      # Database migration scripts and utilities
    ├── news/           # News domain logic and models
    │   └── testdata/   # Test fixtures for news module
    │       └── sql/    # SQL test data
    ├── postgres/       # PostgreSQL database implementation
    ├── router/         # HTTP router and middleware
    └── store/          # Data access layer interface
```

## Installation

### Prerequisites:
- Go version 1.x or later (check with `go version`)
- A code editor or IDE with Go support
- PostgreSQL database (for full functionality)

### Install dependencies:
```bash
go mod tidy
```

## Running the API

Run the API server:
```bash
go run ./cmd/api-server
```

This will start the API server on port 8080 by default.

### Database Migrations

To set up or update the database schema:
```bash
go run ./cmd/migrate
```

## API Endpoints

| Method | Endpoint    | Description                              |
|--------|-------------|------------------------------------------|
| POST   | /news       | Create a new news resource               |
| GET    | /news       | Retrieve a list of all news              |
| GET    | /news/:id   | Get details of a specific news by ID     |
| PUT    | /news/:id   | Update an existing news                  |
| DELETE | /news/:id   | Delete a news                            |

## Testing

Unit tests are crucial for ensuring code quality. You can run your tests with:

```bash
go test ./...
```

## Docker Support

Build and run with Docker:

```bash
# Build the Docker image
docker build -t news-api .

# Run the container
docker run -p 8080:8080 news-api
```

## License

This project is licensed under the MIT License - see the LICENSE file for details.
