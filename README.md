# 🚀 FEM Project Go

A modern Go project developed during the Frontend Masters course, following best practices and clean architecture.

## 📋 About the Project

This project is being developed as part of learning Go, implementing a robust and scalable application with focus on modular structure and code organization.

## 🏗️ Architecture

```
fem-project-go/
├── main.go              # Application entry point
├── go.mod              # Dependency management
├── docker-compose.yml  # Database services configuration
├── internal/           # Internal application code
│   ├── app/           # Application configuration and initialization
│   ├── routes/        # HTTP routes definition
│   ├── api/          # API handlers for workouts
│   └── store/        # Data access layer (in development)
├── database/          # PostgreSQL data volumes
└── README.md         # Project documentation
```

## 🛠️ Technologies Used

- **Go** 1.25.0
- **Chi Router** v5.2.3 - Lightweight HTTP router and URL matcher
- **PostgreSQL** 12.4 - Database for data persistence
- **Docker Compose** - Containerized database services
- **Modular Architecture** with internal packages for clean code organization

## 🔄 CI/CD Pipeline

This project includes a comprehensive CI/CD pipeline that ensures code quality and consistency:

### Pipeline Features
- **Automated Testing**: Runs on every push and pull request to the main branch
- **Go Version**: Uses Go 1.25.0 with dependency caching for faster builds
- **Dependency Validation**: Ensures `go.mod` and `go.sum` are clean and up-to-date
- **Environment Setup**: Validates the presence of required configuration files (`.env_example`)

### Workflow Triggers
- **Push** to `main` branch
- **Pull Requests** targeting `main` branch

The pipeline helps maintain code quality by automatically checking for common issues and ensuring all dependencies are properly managed.

## 📡 API Endpoints

The following endpoints are currently available:

### Workouts
- `GET /health` - Health check endpoint
- `GET /workouts/{id}` - Retrieve a specific workout by ID
- `POST /workouts` - Create a new workout

## 🚀 How to Run

### Prerequisites

- Go 1.25.0 or higher installed
- Git for version control

### Installation

1. Clone the repository:
```bash
git clone https://github.com/jjhonny/fem-project-go.git
cd fem-project-go
```

2. Download dependencies:
```bash
go mod tidy
```

3. Start the database (optional, for development):
```bash
docker-compose up -d
```

4. Run the application:
```bash
go run main.go
```

The API will be available at `http://localhost:8080`

### Testing the API

You can test the endpoints using curl:

```bash
# Health check
curl http://localhost:8080/health

# Get workout by ID
curl http://localhost:8080/workouts/1

# Create workout
curl -X POST http://localhost:8080/workouts \
  -H "Content-Type: application/json" \
  -d '{"name":"Morning Run","duration":30}'
```

## 📝 Development Status

This project is in **active development**. New features and improvements will be added regularly.


## 🤝 Contributing

This is a learning project, but suggestions and improvements are always welcome!

## 📄 License

This project is part of an educational course from Frontend Masters.

---

⭐ **Developed by [Jhonny](https://github.com/jjhonny)** during the Go course at Frontend Masters
