# TaskManagerApi

A CRUD REST API for managing tasks, built in C# with ASP.NET Core, Entity Framework Core, and SQLite. Built as a hands-on project to deepen my understanding of backend development and API design as a QA professional — going beyond testing APIs to actually building one from scratch.

## Overview

This API allows you to create, read, update, and delete tasks, each with a title, due date, and completion status. Data is persisted to a SQLite database using Entity Framework Core, and all endpoints are documented and testable via Swagger UI.

## Tech Stack

- **Language:** C#
- **Framework:** ASP.NET Core Web API
- **ORM:** Entity Framework Core
- **Database:** SQLite
- **API Documentation/Testing:** Swagger UI (Swashbuckle)
- **API Testing:** Postman

## Features

- Full CRUD functionality (Create, Read, Update, Delete) for tasks
- RESTful endpoint design
- SQL-backed data persistence with EF Core migrations
- Interactive API documentation via Swagger UI
- Postman collection for endpoint testing and validation

## Endpoints

| Method | Endpoint            | Description              |
|--------|----------------------|---------------------------|
| GET    | `/api/Tasks`         | Get all tasks             |
| GET    | `/api/Tasks/{id}`    | Get a single task by ID   |
| POST   | `/api/Tasks`         | Create a new task         |
| PUT    | `/api/Tasks/{id}`    | Update an existing task   |
| DELETE | `/api/Tasks/{id}`    | Delete a task              |

### Task Model

```json
{
  "id": 1,
  "title": "Learn C#",
  "isComplete": false,
  "dueDate": "2026-08-15T00:00:00"
}
```

## Getting Started

### Prerequisites
- [.NET 8 SDK](https://dotnet.microsoft.com/download)
- Visual Studio 2022 (or any C# IDE)

### Running Locally

1. Clone the repository
   ```
   git clone https://github.com/brianna-torbert/TaskManagerApi.git
   ```
2. Open `TaskManagerApi.sln` in Visual Studio
3. Restore NuGet packages (Visual Studio does this automatically on build)
4. Run the database migrations:
   ```
   Add-Migration InitialCreate
   Update-Database
   ```
5. Press **F5** to run the project
6. Navigate to `https://localhost:{port}/swagger` to view and test the API endpoints

## What I Learned

Building this project from scratch — not just testing an existing API — gave me a much deeper understanding of how backend systems actually work, which directly informs how I approach testing:

- Setting up Entity Framework Core migrations and troubleshooting a NuGet package warning that was silently blocking the database migration from completing
- Diagnosing why Swagger UI wasn't rendering by default (the newer ASP.NET Core template uses a different OpenAPI tool) and integrating Swashbuckle to add it
- Designing a clean, RESTful CRUD API structure from the ground up
- Validating and testing each endpoint using both Swagger UI and Postman

## Future Improvements

- Add authentication/authorization (e.g., basic login flow)
- Migrate from SQLite to PostgreSQL for production-scale data validation practice
- Add unit and integration test coverage
- Deploy to Azure

## Author

**Brianna H. Torbert**
[LinkedIn](https://linkedin.com/in/briannahtorbert) | [GitHub](https://github.com/brianna-torbert)
