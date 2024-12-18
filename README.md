# Task Management Web Application

This is a comprehensive task management system that empowers users to efficiently organize their tasks. The application utilizes **Spring Boot** on the backend and **MySQL** as the database.

## Features

### User Authentication 
- Users can register and log in to access the system securely.
- Authentication ensures that only authorized users can perform operations.

### Task Operations 
- **Add Tasks:** Users can effortlessly add new tasks to the system.
- **View Tasks:** A user-friendly interface allows for quick and easy reference to all tasks.
- **Edit Tasks:** Users have the flexibility to modify task details as needed.
- **Delete Tasks:** Unwanted tasks can be removed to keep the task list organized.
- **Mark as Complete:** Users can mark tasks as complete for effective progress tracking.

## Tech Stack
- **Server:** Java, Spring Boot  
- **Database:** MySQL

## Architecture
The Task Management System follows a client-server architecture. The backend is built using **Spring Boot** and handles all business logic and database operations. **MySQL** is used as the database to store task-related data.

## Modules
- **Backend:** Contains the Java and Spring Boot application responsible for handling business logic and database operations.
- **Database:** Contains the MySQL database schema and scripts for creating and managing the database.

## Project Setup

### Backend Setup
1. Clone the repository.
2. Navigate to the backend directory.
3. Configure the MySQL database connection in `application.properties`.
4. Run the Spring Boot application using your IDE or the command line.

### Database Setup
1. Create a MySQL database.
2. Execute the database schema script provided in the database directory to create the necessary tables.
3. Update the database connection details in the backend `application.properties`.

## API Endpoints Documentation

### 1. Create Task
- **Endpoint:** `POST http://localhost:8080/api/v1/tasks/user/1`
- **Description:** Creates a new task for the specified user.
- **Request Body:**
  ```json
  {
    "task": "go to swim",
    "details": "go to swim"
  }
  
- **Response Body:**
   ```json
   {
    "message": "Task Saved",
   "data": {
    "id": 1,
    "task": "go to swim",
    "details": "go to swim",
    "completed": false,
    "taskCreatedAt": "Timestamp",
    "user": {
      "userId": 1,
      "username": "sandesh",
      "email": "sandesh@gmail.com"
        }
      }
   }


### 2. Get Task by ID
- **Endpoint**: GET- `http://localhost:8080/api/v1/tasks/1`
- **Description**: Retrieves a task by its ID.
- Response Body:
```json
{
  "message": "Found task",
  "data": {
    "id": 1,
    "task": "go to swim",
    "details": "go to swim",
    "completed": false,
    "taskCreatedAt": "Timestamp",
    "user": {
      "userId": 1,
      "username": "sandesh",
      "email": "sandesh@gmail.com"
    }
  }
}


```
### 3. Get All Tasks for User
- **Endpoint**: GET- `http://localhost:8080/api/v1/tasks/user/1`
- **Description**: Retrieves all tasks for the specified user.
- Response Body:
```json

[
  {
    "id": 1,
    "task": "go to swim",
    "details": "go to swim",
    "completed": false,
    "taskCreatedAt": "Timestamp",
    "user": {
      "userId": 1,
      "username": "sandesh",
      "email": "sandesh@gmail.com"
    }
  },
  {
    "id": 2,
    "task": "play cricket",
    "details": "play cricket",
    "completed": true,
    "taskCreatedAt": "Timestamp",
    "user": {
      "userId": 1,
      "username": "sandesh",
      "email": "sandesh@gmail.com"
    }
  }
]

```
### 4. Update Task
- **Endpoint**: PUT- `http://localhost:8080/api/v1/tasks/1`
- **Description**: Updates the details of a task.
- Request Body:
```json

{
  "task": "go to swim in the afternoon",
  "details": "go to swim in the afternoon"
}
```
- Response Body:
```json

{
  "message": "Task updated!",
  "data": {
    "id": 1,
    "task": "go to swim in the afternoon",
    "details": "go to swim in the afternoon",
    "completed": false,
    "taskCreatedAt": "Timestamp",
    "user": {
      "userId": 1,
      "username": "sandesh",
      "email": "sandesh@gmail.com"
    }
  }
}

```

### 5. Delete Task
- **Endpoint**: DELETE- `http://localhost:8080/api/v1/tasks/1`
- **Description**: Deletes a task by its ID.
- Response Body:
```json

{
  "message": "Task deleted successfully"
}

```
