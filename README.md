# 🎓 Student Management API

A high-performance, modern Full-Stack application built with **Spring Boot** and a **Glassmorphism Frontend**. This project provides a robust RESTful API for student data management with a real-time monitoring dashboard.

---

## 🚀 Quick Access Links

### 🖥️ Frontend & Monitoring
*   **[Main Dashboard](http://localhost:8080/index.html)** - Live monitoring and data visualization.
*   **[API Health Check](http://localhost:8080/api/students)** - Direct JSON output of the student records.

### 🛠️ Backend Development Tools
*   **[Swagger UI Documentation](http://localhost:8080/swagger-ui/index.html)** - Interactive API explorer (OpenAPI 3.0).
*   **[H2 Database Console](http://localhost:8080/h2-console)** - In-memory database browser.
    *   *JDBC URL:* `jdbc:h2:mem:testdb`
    *   *Username:* `sa`
    *   *Password:* (blank)

---

## 🏗️ Architecture Overview

The project is split into two main layers, separated by a RESTful boundary:

### 🔹 Backend (Spring Boot)
Located in `src/main/java/studentapi/`, the backend follows the standard Controller-Service-Repository pattern:
*   **Entity Layer**: JPA models (`Student.java`) with Jakarta Validation constraints.
*   **Controller Layer**: REST endpoints for CRUD operations.
*   **Data Layer**: Spring Data JPA for H2 in-memory storage.
*   **Validation**: Automatic 400 Bad Request handling for invalid inputs.

### 🔸 Frontend (Static Dashboard)
Located in `src/main/resources/static/`, the frontend is a zero-dependency modern UI:
*   **Live Connection Monitoring**: Uses a polling mechanism to verify backend uptime.
*   **Async Data Fetching**: Retrieves and renders student data using the Fetch API.
*   **Interactive Simulation**: Includes an "Add Test" feature to verify POST request cycles.
*   **Rich Aesthetics**: Custom CSS with Google Fonts (Outfit), smooth animations, and glassmorphism cards.

---

## 🛠️ Running the Project

1.  **Ensure Java 25** is installed.
2.  Run the application using the Maven Wrapper:
    ```bash
    sh mvnw spring-boot:run
    ```
3.  Navigate to `http://localhost:8080/index.html` in your browser.

---

## ☁️ Deployment (Render/Heroku/Cloud)

The project includes a **Dockerfile** for easy deployment.

### On Render:
1.  Connect your GitHub repository.
2.  Render will detect the `Dockerfile` and set the **Runtime** to `Docker`.
3.  Set the **Environment Variable** `PORT` to `8080` (if not detected).
4.  **Important**: The Java version is set to **21** for maximum platform compatibility.

---

## 📡 API Endpoints Summary

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/api/students` | Get all students |
| `POST` | `/api/students` | Create a new student |
| `GET` | `/api/students/{id}` | Get student by ID |
| `PUT` | `/api/students/{id}` | Update student data |
| `DELETE` | `/api/students/{id}` | Remove a student |
