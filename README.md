# Go Fiber Docker CRUD API

A RESTful API built with Go, the [Fiber](https://gofiber.io/) web framework, and Docker. This project features CRUD operations, auto-generated Swagger documentation, and a GitHub Actions CI/CD pipeline. It is ready to be deployed on Render.

## Features

- **Go Fiber**: Extremely fast web framework for Go.
- **CRUD Operations**: Complete Create, Read, Update, and Delete endpoints for a Todo list.
- **Swagger Documentation**: Interactive API documentation generated automatically.
- **Dockerized**: Includes a `Dockerfile` for easy containerization and deployment.
- **CI/CD Pipeline**: GitHub Actions configured for building and testing.

## Prerequisites

- [Go](https://golang.org/doc/install) 1.21 or later
- [Docker](https://docs.docker.com/get-docker/) (optional, for containerization)
- [Swag CLI](https://github.com/swaggo/swag) (for generating Swagger docs)

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/go-fiber-todo-api.git
cd go-fiber-todo-api
```

### 2. Running locally with Go

First, install dependencies and generate the Swagger documentation:

```bash
go mod tidy
go install github.com/swaggo/swag/cmd/swag@latest
swag init
```

Then, run the application:

```bash
go run main.go
```

The server will start on port `3000` (or the port defined in your `PORT` environment variable).

### 3. Running with Docker

To build and run the Docker container:

```bash
docker build -t fiber-app .
docker run -p 3000:3000 fiber-app
```

## API Documentation (Swagger)

Once the application is running, you can access the interactive Swagger UI to test the endpoints at:

```
http://localhost:3000/swagger/index.html
```

## Deployment on Render

This project is configured to be easily deployable on [Render](https://render.com/).

1. Push your code to a GitHub repository.
2. Go to the [Render Dashboard](https://dashboard.render.com/) and create a new **Web Service**.
3. Connect your GitHub repository.
4. Render will automatically detect the `Dockerfile`. Ensure the Environment/Runtime is set to **Docker**.
5. Click **Create Web Service**. 
6. Render will build and deploy your application. Once finished, you can access your API via the provided `.onrender.com` URL.

