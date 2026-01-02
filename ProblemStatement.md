Problem: Build a RESTful API for managing tasks (create, read, update, delete, assign to users, mark as completed). Demonstrate scalable architecture for enterprise apps, with separation of domain logic from infrastructure.
This shows you can design maintainable systems using modern patterns (inspired by Microsoft’s eShopOnWeb and Jason Taylor’s CleanArchitecture template).
Solution Outline:
•  Use Clean Architecture (4 layers: Domain, Application, Infrastructure, Presentation/API).
•  Domain: Entities (Task, User), Value Objects (DueDate), Domain Events (TaskCompletedEvent).
•  Application: CQRS with MediatR (Commands: CreateTaskCommand; Queries: GetTasksQuery).
•  Infrastructure: EF Core for persistence, Repository pattern.
•  API: ASP.NET Core Minimal APIs or Controllers, Swagger, FluentValidation.
•  Extras: Logging with Serilog, basic authentication (JWT), unit tests with xUnit + Moq.
