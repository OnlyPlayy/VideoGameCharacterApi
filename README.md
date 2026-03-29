# VideoGameCharacterApi

Compact, production‑style REST API built with modern .NET for managing video game characters.

What this project does
- Implements a RESTful CRUD API for `Character` resources (Name, Game, Role).
- Persistent storage with Entity Framework Core migrations and SQL Server (connection string in `appsettings.json`).
- Exposes endpoints implemented in `Controllers/VideoGameCharactersController.cs` and business logic in `Services/VideoGameCharacterService.cs`.
- Includes an HTTP client sample in `VideoGameCharacterApi.http` for quick manual testing.

Tech & tools used
- .NET 10 (project target)
- C# 14 language features and top-level statements
- Entity Framework Core (migrations and `DbContext` in `Data/AppDbContext.cs`)
- SQL Server / SQLExpress (see `appsettings.json`) for persistence
- Dependency Injection (built-in .NET DI)
- OpenAPI tooling (registered in `Program.cs`)
- Scalar.AspNetCore (project includes `AddOpenApi()` / API reference mapping)
- Visual Studio launch profiles (`Properties/launchSettings.json`)

How to run locally
1. Update the connection string in `appsettings.json` if needed (default points to `localhost\SQLExpress`).
2. Apply migrations and create the database (requires the EF CLI or Package Manager Console):
   - `dotnet ef database update` (from project folder)
3. Run the project:
   - `dotnet run`
4. Use `VideoGameCharacterApi.http` or any HTTP client (Postman, curl) to exercise endpoints. OpenAPI endpoints are available in Development mode (configured in `Program.cs`).


Project structure (high level)
- `Controllers/` — HTTP endpoints
- `Services/` — business logic and persistence orchestration
- `Data/` — EF `DbContext` and migrations
- `Dtos/` — request/response shapes
- `Migrations/` — EF Core migrations history

License / Notes
- This project is a personal portfolio sample. Feel free to copy ideas and extend it with authentication, swagger examples, and tests to demonstrate further skills.