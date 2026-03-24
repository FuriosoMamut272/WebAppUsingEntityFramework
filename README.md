# Creating an MVC Web App using Entity Framework Database First

**Author:** Mateo Isaza

---

## 📌 Description

This project demonstrates how to create an MVC Web Application using the **Database First** approach with Entity Framework Core and SQL Server. It includes database creation, scaffolding, and generation of models, controllers, and views.

---

## 🗄️ Database Setup (SQL Server 2021)

Run the following SQL script to create the database and tables:

```sql
CREATE DATABASE SampleDb;
GO

USE SampleDb;
GO

CREATE TABLE Categories(
    CategoryId INT IDENTITY(1,1) PRIMARY KEY,
    Name NVARCHAR(100) NOT NULL
);
GO

CREATE TABLE Products(
    ProductId INT IDENTITY(1,1) PRIMARY KEY,
    Name NVARCHAR(100) NOT NULL,
    Price DECIMAL(18,2) NOT NULL,
    CategoryId INT FOREIGN KEY REFERENCES Categories(CategoryId)
);
GO
```

---

## 📦 Required Packages

Install the following packages using Package Manager Console or NuGet:

```powershell
Install-Package Microsoft.EntityFrameworkCore.SqlServer
Install-Package Microsoft.EntityFrameworkCore.Design
Install-Package Microsoft.EntityFrameworkCore.Tools
```

---

## ⚙️ Scaffolding DbContext and Models

Run the following command to generate the DbContext and Models from the database:

```powershell
Scaffold-DbContext "Server=DESKTOP-GJDFMRJ\SQLEXPRESS01;Database=SampleDb;Trusted_Connection=True;TrustServerCertificate=True;" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Models -ContextDir Data -DataAnnotations -Force
```

---

## 🧱 Project Structure

* **Models/** → Contains entity classes generated from the database
* **Data/** → Contains the DbContext
* **Controllers/** → Handles application logic
* **Views/** → UI generated using MVC scaffolding

---

## 🖥️ Application Views

After generating Controllers and Views using Entity Framework, the application allows:

* Managing Categories (Create, Read, Update, Delete)
* Managing Products linked to Categories
* Displaying relational data in views

*(Insert application screenshots here if needed)*

---

##  Technologies Used

* ASP.NET Core MVC
* Entity Framework Core
* SQL Server 2021

---

##  Notes

* This project uses the **Database First** approach.
* Ensure SQL Server is running before executing scaffolding.
* Update the connection string if your server name differs.

---
