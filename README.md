# CarApi

CarApi is a simple ASP.NET Core Web API for managing a collection of cars and their owners. The project targets **.NET 7** and uses Entity Framework Core with SQL Server (or another provider) for data storage. Basic CRUD endpoints are provided for both `User` and `Car` entities and initial sample data is seeded via `DbInitializer`.

## Prerequisites

- [.NET 7 SDK](https://dotnet.microsoft.com/download)
- A SQL Server or compatible database (update the connection string in `appsettings.json`)

## Getting Started

1. Clone the repository and restore dependencies:

   ```bash
   dotnet restore
   ```

2. Update the connection string `MariaDbConnectionString` inside `appsettings.json` to match your database settings.

3. Apply the Entity Framework migrations to create the database schema:

   ```bash
   dotnet ef database update
   ```

4. Run the API:

   ```bash
   dotnet run
   ```

   The API will by default launch on `http://localhost:5182` (or `https://localhost:7252`) and expose Swagger UI for testing the endpoints.

## Available Endpoints

### Cars

- `GET /api/car` – List all cars
- `GET /api/car/{id}` – Get a specific car
- `POST /api/car` – Add a new car
- `PUT /api/car/{id}` – Update an existing car
- `DELETE /api/car/{id}` – Remove a car

### Users

- `GET /api/user` – List all users
- `GET /api/user/{id}?includeCars=true` – Get a user with optional car data
- `POST /api/user` – Add a new user
- `PUT /api/user/{id}` – Update an existing user
- `DELETE /api/user/{id}` – Remove a user

## Seeding Data

`DbInitializer` seeds two example users and two example cars on model creation. This allows the API to be used immediately after applying the migrations.

## License

This project does not currently include a license file. Consider adding one if you plan to share or distribute the code.

