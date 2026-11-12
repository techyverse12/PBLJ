# Student Management System

This is a simple Student Management REST API made using Java, Spring Boot, Spring Data JPA and MySQL.

## Features

- Add a student
- View all students
- View one student using ID
- Update student details
- Delete a student
- Find students by course

## Technologies Used

- Java 17
- Spring Boot
- Spring Data JPA
- MySQL
- Maven
- Postman (for API testing)

## Run the project

1. Install Java 17, Maven and MySQL.
2. Create the database:

   ```sql
   CREATE DATABASE student_db;
   ```

3. Open `src/main/resources/application.properties` and set your MySQL username and password. You can also set the environment variables `DB_USERNAME`, `DB_PASSWORD` and `DB_URL`.
4. Run the application:

   ```bash
   mvn spring-boot:run
   ```

The API will start at `http://localhost:8080`.

## API endpoints

| Method | URL | Purpose |
|---|---|---|
| POST | `/api/students` | Add a student |
| GET | `/api/students` | Get all students |
| GET | `/api/students/{id}` | Get a student by ID |
| PUT | `/api/students/{id}` | Update a student |
| DELETE | `/api/students/{id}` | Delete a student |
| GET | `/api/students/course/{course}` | Get students by course |

## Sample JSON

Use this JSON body for POST and PUT requests:

```json
{
  "name": "Aarav Sharma",
  "email": "aarav@example.com",
  "course": "CSE",
  "age": 21
}
```

## HTTP status codes

- `201 Created` - student added successfully
- `200 OK` - data retrieved or updated
- `204 No Content` - student deleted
- `400 Bad Request` - invalid input
- `404 Not Found` - student ID does not exist
- `409 Conflict` - duplicate email

## Notes

The database table is created/updated by Hibernate when the application starts. Test each endpoint in Postman after starting the application.
