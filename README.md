# Task Management API - Clean Architecture + CQRS Basics with CQRS (MediatR) in .NET 8

![.NET 8](https://img.shields.io/badge/.NET-8.0-blue.svg)
![Clean Architecture](https://img.shields.io/badge/Architecture-Clean%20Architecture-brightgreen.svg)
![CQRS](https://img.shields.io/badge/Pattern-CQRS%20%2B%20MediatR-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

A production-ready **Task Management REST API** built using **Clean Architecture** principles and **CQRS pattern** with **MediatR**. This project demonstrates modern .NET best practices and is designed to showcase senior-level / architect experience on GitHub.

Perfect for interviews when discussing scalable, maintainable, and testable enterprise application design.

## 🚀 Features

- Clean Architecture (4 layers: Domain → Application → Infrastructure → Presentation)
- CQRS pattern using **MediatR**
- Entity Framework Core with SQL Server (LocalDB)
- Repository Pattern
- FluentValidation ready (extensible)
- RESTful endpoints for CRUD operations on Tasks
- Swagger/OpenAPI documentation
- Layered dependency flow (Dependency Inversion Principle)
- Ready for unit/integration testing

## 🏗️ Architecture Overview

```mermaid
graph TD
    A[Presentation Layer
TaskManagement.Api] -->|depends on| B[Application Layer
TaskManagement.Application]
    A -->|depends on| C[Infrastructure Layer
TaskManagement.Infrastructure]
    B -->|depends on| D[Domain Layer
TaskManagement.Domain]
    C -->|depends on| B
    C -->|depends on| D

    style D fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#bbf,stroke:#333
    style C fill:#bfb,stroke:#333
    style A fill:#fbb,stroke:#333
	•	Domain: Pure business entities and rules (no dependencies)
	•	Application: Use cases, commands, queries, interfaces (MediatR handlers)
	•	Infrastructure: EF Core, repositories, external services
	•	Presentation (API): Controllers, Minimal APIs, Swagger

📋 API Endpoints
Method
Endpoint
Description
GET
/api/tasks
Get all tasks
GET
/api/tasks/{id}
Get task by ID
POST
/api/tasks
Create a new task
PUT
/api/tasks/{id}
Update an existing task
DELETE
/api/tasks/{id}
Delete a task (planned)
Example Request (POST)
{
  "title": "Implement Clean Architecture",
  "description": "Refactor legacy code to layered structure",
  "dueDate": "2026-02-01T00:00:00Z",
  "assignedToUserId": "3fa85f64-5717-4562-b3fc-2c963f66afa6"
}
🛠️ Tech Stack
	•	.NET 8 (Latest LTS)
	•	ASP.NET Core Web API
	•	Entity Framework Core
	•	MediatR for CQRS
	•	SQL Server / LocalDB
	•	Swagger (Swashbuckle)
⚙️ Getting Started
Prerequisites
	•	.NET 8 SDK
	•	SQL Server or LocalDB (included with Visual Studio)
	•	Visual Studio 2022 / VS Code / Rider
Setup & Run
	1	Clone the repository
git clone https://github.com/yourusername/TaskManagement.Api.git
cd TaskManagement.Api
	2	Apply EF Core Migrations
# From the solution root
dotnet ef database update --project TaskManagement.Infrastructure --startup-project TaskManagement.Api
First time? Make sure dotnet-ef tool is installed:
dotnet tool install --global dotnet-ef
	3	Run the API
dotnet run --project TaskManagement.Api
	4	Open Swagger UI
Visit: https://localhost:7294/swagger (port may vary)
🧪 Testing
Project is structured for easy addition of:
	•	Unit tests (xUnit + Moq)
	•	Integration tests (WebApplicationFactory)
	•	Behavioral tests on domain logic
(Tests coming soon or open for contributions!)
🎯 What This Project Demonstrates is 🤷

	•	Strict separation of concerns and dependency inversion
	•	Domain model encapsulates business rules (e.g., immutable updates via methods)
	•	Scalable CQRS foundation (easy to add event sourcing, read models later)
	•	Ready for horizontal scaling, microservices evolution
	•	Follows industry standards used in large-scale .NET systems (Microsoft eShop, Jason Taylor’s templates)

📈 Future Enhancements (Ideas)
	•	JWT Authentication & Authorization
	•	FluentValidation pipeline
	•	AutoMapper / Mapster for DTO mapping
	•	Docker + docker-compose
	•	Event-driven architecture with Domain Events
	•	Background workers (Hangfire / Quartz)
	•	Unit & Integration Tests
	•	Logging with Serilog
	•	Health Checks & Monitoring

🤝 Contributing
Contributions are welcome! Feel free to open issues or PRs.

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

Built by a Sr. Tech Lead to showcase real-world architectural skills in .NET.

⭐ Star this repo if you found it useful for learning Clean Architecture !

Happy Coding! 🚀