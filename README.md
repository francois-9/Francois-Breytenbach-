# EmployeeWebApplication

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 17.1.2.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.

## Front end

Run the following commands 

```
npm install
```

```
npm install -g @angular/cli
```


## Database setup 

You will need your own local or remote mysql database.

If you want a local database they you need to download the following.
SSMS
https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16
SQL server
https://www.microsoft.com/en-za/sql-server/sql-server-downloads

After creating the database go to appsettings file under

BreytieBackend_re\BreytieBackend_re\appsettings.json

and paste your connection string on Default connection

 "ConnectionStrings": {
    "DefaultConnection": "YourConnectionStringGoesHere"
  },

Here is a database configuration script to help create the Database fast. 

```
CREATE DATABASE EmployeeDatabase;

USE EmployeeDatabase;

CREATE TABLE [dbo].[Employees] (
    [EmployeeID]  NVARCHAR (50) NOT NULL,
    [FirstName]   NVARCHAR (50) NULL,
    [LastName]    NVARCHAR (50) NULL,
    [Contact]     NVARCHAR (50) NULL,
    [Email]       NVARCHAR (50) NULL,
    [DateOfBirth] DATETIME      NULL,
    [Street]      NVARCHAR (50) NULL,
    [City]        NVARCHAR (50) NULL,
    [PostalCode]  INT           NULL,
    [Country]     NVARCHAR (50) NULL,
    PRIMARY KEY CLUSTERED ([EmployeeID] ASC)
);
```

# Employees API

This API is built with .NET Core and provides CRUD operations for managing employees.

## Endpoints

### GET /api/employees

Returns a list of all employees.

### GET /api/employees/{id}

Returns the employee with the specified ID. If no employee with that ID exists, a 404 Not Found status is returned.

### POST /api/employees

Creates a new employee. The ID of the new employee is generated automatically.

### PUT /api/employees/{id}

Updates the employee with the specified ID. If the ID in the URL does not match the ID in the body, a 400 Bad Request status is returned.

### DELETE /api/employees/{id}

Deletes the employee with the specified ID. If no employee with that ID exists, a 404 Not Found status is returned.

## System Requirements

- .NET Core 3.1 or later
- An IDE such as Visual Studio or Visual Studio Code

## Required Applications

- Postman (for testing API endpoints)
- SQL Server (for database)
