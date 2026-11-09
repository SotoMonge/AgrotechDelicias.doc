# AgrotechDelicias

**AgrotechDelicias Documentation**  
*Intelligent agricultural irrigation optimization system.*

An intelligent agricultural irrigation optimization system designed to automate and determine the optimal irrigation window for registered crops. The system evaluates soil moisture via telemetry and integrates this data through a Web API with predictive weather data from external meteorological APIs.

---

## 🚀 Key Features

*   **Telemetry Evaluation:** Real-time monitoring and evaluation of soil moisture.
*   **Weather Integration:** Blends telemetry data with predictive weather insights from external meteorological APIs (**OpenWeatherMap**).
*   **Smart Automation:** Automatically determines and schedules the optimal irrigation window for registered crops.
*   **Decoupled Architecture:** Modern, separate frontend and backend communication.

---

## 🏗️ Architecture & Tech Stack

The system is built using a decoupled architecture, ensuring scalability and clean separation of concerns:

### Frontend
*   **Framework:** Angular (Decoupled Single Page Application - SPA).
*   **Communication:** Consumes the backend via injected services (`HttpClient`).
*   **Data Exchange:** Formatted exclusively in **JSON**.

### Backend & Database
*   **Framework:** .NET Web API.
*   **ORM:** Entity Framework (EF Core).
*   **Database (Development):** Microsoft SQL Server.
*   **Database (Production/Cloud):** Azure SQL Database.

---

## ⚙️ Configuration & Environment Variables

To run this project locally or deploy it to the cloud, you need to configure the following environment settings.

### Backend (`appsettings.json`)
Add your database connection strings and external API credentials:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=YOUR_SQL_SERVER;Database=AgrotechDeliciasDb;Trusted_Connection=True;TrustServerCertificate=True;",
    "AzureSqlConnection": "Server=tcp:YOUR_AZURE_SERVER.database.windows.net,1433;Initial Catalog=AgrotechDeliciasDb;Persist Security Info=False;User ID=YOUR_USERNAME;Password=YOUR_PASSWORD;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection Timeout=30;"
  },
  "OpenWeatherMap": {
    "ApiKey": "YOUR_OPENWEATHERMAP_API_KEY",
    "BaseUrl": "https://openweathermap.org"
  }
}
```

---

## 🛠️ Getting Started

### Prerequisites
*   [.NET SDK](https://microsoft.com) (Latest LTS recommended)
*   [Node.js & npm](https://nodejs.org)
*   [Angular CLI](https://angular.dev) (`npm install -g @angular/cli`)
*   [SQL Server Express](https://microsoft.com) or an active Azure SQL instance.

### Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com
   cd AgrotechDelicias
   ```

2. **Database Setup (Migrations):**
   Navigate to the backend project directory and apply the Entity Framework migrations to generate the database schema:
   ```bash
   cd backend
   dotnet ef database update
   ```

3. **Run the Backend System:**
   ```bash
   dotnet run
   ```

4. **Setup and Run the Frontend System:**
   Open a new terminal window, navigate to the frontend folder, install dependencies, and start the development server:
   ```bash
   cd frontend
   npm install
   ng serve
   ```
   The application will be accessible locally at `http://localhost:4200`.
