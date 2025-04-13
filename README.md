# Base Node.js Project Template

This is a **Base Node.js Project Template**, designed with best practices and project management principles. It includes Sequelize CLI for easy database management. Feel free to modify it as needed.

## 📁 Project Structure

```
src/
   config/              # Configuration files (dotenv, logging, server setup)
   controllers/         # Request handlers (business logic)
   middlewares/         # Custom middleware functions
   migrations/          # Database migration scripts (auto-generated by Sequelize CLI)
   models/              # ORM models for database tables (auto-generated)
   repositories/        # Data access layer (handling DB queries)
   routes/              # API route definitions
   seeders/             # Data seeding scripts (auto-generated)
   services/            # Business logic layer
   utils/               # Utility functions
```

## 🚀 Features

- Organized MVC architecture
- Express.js framework
- **Sequelize ORM with CLI** for database management
- MySQL integration
- Logging with Winston
- Environment variable management with Dotenv

## 🛠 Setup

### 1⃣ Install Dependencies

```sh
git clone <repo-url>
cd base_node_js_project_template
npm install
```

### 2⃣ Initialize Sequelize

Before configuring the database, initialize Sequelize CLI by running:

```sh
npx sequelize init
```

This will generate necessary folders (`config`, `models`, `migrations`, `seeders`) inside `src/`.

### 3⃣ Configure the Database

Inside `src/config/`, a **config.json** file is generated, where we define database settings:

```json
{
  "development": {
    "username": "root",
    "password": null,
    "database": "database_development",
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
  "test": {
    "username": "root",
    "password": null,
    "database": "database_test",
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
  "production": {
    "username": "root",
    "password": null,
    "database": "database_production",
    "host": "127.0.0.1",
    "dialect": "mysql"
  }
}
```

Modify **username**, **password**, and **database** based on your MySQL setup.

### Understanding Development, Test, and Production Databases

- **Development (`database_development`)**  
  Used for daily development and debugging. Contains test data for local testing.

- **Test (`database_test`)**  
  Used for running automated tests. Typically, data is reset frequently to maintain a clean testing environment.

- **Production (`database_production`)**  
  Used in the live application. This should be configured with real database credentials and **never** include test data.

To use different environments, set the `NODE_ENV` variable:

```sh
NODE_ENV=development  # For local development
NODE_ENV=test         # Before running tests
NODE_ENV=production   # In a live environment
```

## 🚀 Running the Project

### Start in Development Mode

```sh
npm run dev
```

This will use **nodemon** to automatically restart the server on changes.

### Running Migrations

If you modify your models, you need to run migrations to apply changes to the database:

```sh
npx sequelize db:migrate
```

### Running Seeders

To populate the database with initial data, run:

```sh
npx sequelize db:seed:all
```

## 👆 Dependencies

- **Express.js** – Web framework
- **Sequelize + Sequelize CLI** – ORM for MySQL
- **Dotenv** – Environment variable management
- **Winston** – Logging
- **Nodemon** – Auto-restarting development server

## 🤝 Contributing

Feel free to contribute by opening an issue or submitting a pull request.
