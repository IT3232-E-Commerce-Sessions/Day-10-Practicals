# Employee Management System - Spring Boot REST API

## Overview

This project is a comprehensive RESTful API for managing departments, employees, and projects within an organization. It implements full CRUD operations with proper error handling and relationship management between entities.

## Features

- Department management (create, read, update, delete)
- Employee management with department assignments
- Project management with employee allocations
- Proper error handling and validation
- RESTful design with HTTP status codes
- JPA/Hibernate for database operations

## Technologies

- Java 17
- Spring Boot 3.1.0
- Spring Data JPA
- Hibernate
- Maven
- MySQL Database
- Lombok
- Jackson

## Project Structure

```
src/
├── main/
│   ├── java/
│   │   └── com/
│   │       └── system/
│   │           └── sampleapp/
│   │               ├── controller/       # REST controllers
│   │               ├── model/            # JPA entities
│   │               ├── repo/             # Spring Data repositories
│   │               ├── service/          # Business logic services
│   │               └── SampleappApplication.java # Main class
│   └── resources/
│       └── application.properties        # Configuration
└── test/                                # Test classes
```

## Exercises Implementation

### 1. Repository Implementation

Created Spring Data JPA repositories for all models:

- DepartmentRepo: Manages department entities
- EmployeeRepo: Handles employee operations
<!-- - ProjectRepo: Controls project data -->

### 2. Service Layer Implementation

Developed service classes with full CRUD operations:

- DepartmentService: Handles department business logic
- EmployeeService: Manages employee operations with department relationships
<!-- - ProjectService: Controls project management with employee allocations -->

### 3. CRUD Operations

Implemented comprehensive CRUD functionality:

- Create: Add new entities with proper validation
- Read: Retrieve single entities and collections
- Update: Modify existing entities with relationship management
- Delete: Remove entities with proper error handling

### 4. Controller Implementation

Built REST controllers with proper endpoint mapping:

- DepartmentController: Manages department resources
- EmployeeController: Handles employee operations
<!-- - ProjectController: Controls project management -->

### 5. ResponseEntity Usage

Wrapped all responses with proper HTTP status codes:

- 200 OK for successful requests
- 201 Created for resource creation
- 400 Bad Request for invalid inputs
- 404 Not Found for missing resources
- 409 Conflict for duplicate entries
- 500 Internal Server Error for unexpected issues

## API Documentation

### Department Endpoints

| Method | Endpoint              | Description          |
| ------ | --------------------- | -------------------- |
| POST   | /api/departments      | Create department    |
| GET    | /api/departments/{id} | Get department by ID |
| GET    | /api/departments      | Get all departments  |
| PUT    | /api/departments/{id} | Update department    |
| DELETE | /api/departments/{id} | Delete department    |

### Employee Endpoints

| Method | Endpoint            | Description        |
| ------ | ------------------- | ------------------ |
| POST   | /api/employees      | Create employee    |
| GET    | /api/employees/{id} | Get employee by ID |
| GET    | /api/employees      | Get all employees  |
| PUT    | /api/employees/{id} | Update employee    |
| DELETE | /api/employees/{id} | Delete employee    |

## Setup Instructions

1. **Prerequisites**:

   - Java 17 JDK
   - MySQL 8.x
   - Maven 3.8+

2. **Database Setup**:

   ```sql
   CREATE DATABASE company_db;
   use company_db;
   ```

3. **Configuration** (`application.properties`):

   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/company_db
   spring.datasource.username=appuser
   spring.datasource.password=password
   spring.jpa.hibernate.ddl-auto=update
   ```

4. **Build and Run**:
   ```bash
   mvn clean package
   java -jar target/sampleapp-0.0.1-SNAPSHOT.jar
   ```

## Best Practices Implemented

- Layered architecture (Controller-Service-Repository)
- Transaction management
- Proper HTTP status codes
- Comprehensive error handling
- RESTful resource naming
- Input validation
- Secure database configuration
- Relationship management in JPA entities
