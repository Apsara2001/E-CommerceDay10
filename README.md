# E-CommerceDay10
# Department Management Service

A Spring Boot RESTful API for managing department records with full CRUD support, data validation, and global exception handling. Built using layered architecture and JPA integration.

---

##  Overview

This project is designed for institutions or organizations that require a backend service to manage department information. It emphasizes clean design, validation, and consistent REST principles.

---

##  Architecture Layers

- 📦 **Model Layer** – JPA entities with appropriate annotations
- 💾 **Repository Layer** – Interfaces using Spring Data JPA
- ⚙️ **Service Layer** – Business logic and validations
- 🧱 **Exception Handling** – Centralized error management

---

## Key Features

### 🔧 Department Operations

- ✅ Get all departments
- ✅ Retrieve department by ID
- ✅ Add a new department (with duplicate ID validation)

### 🛡️ Data Validation

- 🔒 Prevents duplicate department IDs
- ✅ Required field checks
- 📬 Clear, consistent HTTP responses

### 🧨 Exception Handling

| Exception | HTTP Status | Message Description |
|-----------|-------------|---------------------|
| EntityNotFoundException | 404 | Department not found |
| DuplicateKeyException   | 400 | Duplicate department ID |
| Exception               | 500 | Generic server error |

---

## 🌐 REST API Endpoints

### 🔍 Get All Departments
```http
GET /api/departments
```
![Screenshot (1135)](https://github.com/user-attachments/assets/1476c891-6fb9-4507-bc49-7609b7ebc8d3)

Returns a list of all departments.

### Get Department by ID
```http
GET /api/departments/{id}
```
![Screenshot (1136)](https://github.com/user-attachments/assets/ac939eee-9945-4c42-be7b-9e5c7fb66640)

Returns a specific department by ID.

**Error Response (404):**

![Screenshot (1133)](https://github.com/user-attachments/assets/42aa5090-59e5-40c0-844e-9db51ee732c4)

### Add New Department
```http
POST /api/departments
```
Creates a new department.

![Screenshot (1137)](https://github.com/user-attachments/assets/2ef22533-4bee-47e3-99c1-3841604b6abe)

**Error Response (400) - Duplicate ID:**

![Screenshot (1134)](https://github.com/user-attachments/assets/7994db7d-97bb-4c1a-900c-4d9251b0d6c2)

---

## ⚙️ Configuration

Update application.properties:

```properties
spring.application.name=departmentapp
spring.datasource.url=jdbc:mysql://localhost:3306/employee
spring.datasource.username=root
spring.datasource.password=
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.jpa.hibernate.ddl-auto=update
```

---

## 🧬 Package Structure

```
lk.ac.vau.fas.ict/
├── model/
│   ├── Department.java
│   └── ErrorResponse.java
├── repo/
│   └── DepartmentRepo.java
├── service/
│   └── DepartmentService.java
└── exceptionHandler/
    └── GenericExceptionHandler.java
```
