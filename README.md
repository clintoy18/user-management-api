# User Management API by Clint Alonzo, Allen Kim Rafaela, Aldrian Orillosa Bahan, Lorenz Lord Toring.

## Project Overview

### Objective
The goal of this project is to build a RESTful API that enables the management of users. The API will provide the ability to perform CRUD operations: Create, Read, Update, and Delete on user data.

### Technologies
- **Backend**: Node.js with TypeScript
- **ORM**: TypeORM for database interactions
- **Database**: MySQL
- **API Framework**: Express.js

### Features
Task Assignments
1. Project Setup & Database Configuration - Clint 
-Manage the main branch and ensure integration of all functionalities.
-Initialize a Node.js project with TypeScript.
-Set up Express.js and TypeORM and all dependecies.
-Configure .env for database credentials.

2. User Model & Migration (TypeORM) - Allen Kim Rafaela
-Define User entity with TypeORM.
-Implement a migration script.
-Run migration and test table creation.

3. CRUD Endpoints (Create & Read) - Aldrian Orillosa Bahan
-Implement POST /users (Create user).
-Implement GET /users (Fetch all users).
-Implement GET /users/:id (Fetch user by ID).

4. CRUD Endpoints (Update & Delete) - Lorenz Lord Toring
-Implement PUT /users/:id (Update user).
-DELETE /users/:id (Delete user).

---
## Setup Instructions

Follow the steps below to get the project up and running locally:

1. Clone the repository:
    ```bash
    git clone https://github.com/clintoy18/user-management-api.git
    ```

2. Navigate into the project folder:
    ```bash
    cd user-management-api
    ```

3. Install the required dependencies:
    ```bash
    npm install
    ```

4. Configure your database settings:
    - Ensure MySQL is installed and running on your local machine.
    - Create a new MySQL database (e.g., `user_management_api`).
    - Update the `config.json` file with your MySQL credentials.

## API Documentation 
API Documentation

1. Register a New User

Endpoint: POST /users

Request Body:

{
  "email": "john.doe@example.com",
  "password": "securepassword",
  "confirmPassword": "securepassword",
  "title": "Mr",
  "firstName": "John",
  "lastName": "Doe",
  "role": "admin"
}

Response:

{
  "id": 1,
  "email": "john.doe@example.com",
  "title": "Mr",
  "firstName": "John",
  "lastName": "Doe",
  "role": "admin",
  "message": "User registered successfully"
}

Validation Rules:

email: Must be valid and unique.

password: Minimum 8 characters, must match confirmPassword.

title: Required, e.g., "Mr", "Ms", "Dr".

firstName & lastName: Required, min 2 characters.

role: Default is "user", valid values are "user" or "admin".

2. Get All Users

Endpoint: GET ALL USERS /users

[
  {
    "id": 1,
    "email": "john.doe@example.com",
    "password": "securepassword",
    "title": "Mr",
    "firstName": "John",
    "lastName": "Doe",
    "role": "admin"
  },
  {
    "id": 2,
    "email": "john1.doe@example.com",
    "password": "securepassword",
    "title": "Mr",
    "firstName": "John",
    "lastName": "Doe",
    "role": "admin"
  }
]

3. Get User by ID

Endpoint: GET /users/:id

Example Request:

GET http://localhost:3000/users/1

Response:

{
  "id": 1,
  "email": "john.doe@example.com",
  "title": "Mr",
  "firstName": "John",
  "lastName": "Doe",
  "role": "admin"
}

Note: Passwords are not included in the response for security.

4. Update User

Endpoint: PUT /users/:id

Request Body:

{
  "email": "john.doe@example.com",
  "title": "Dr",
  "firstName": "John",
  "lastName": "Smith",
  "role": "admin"
}

Response:

{
  "message": "User updated successfully"
}

5. Delete User

Endpoint: DELETE /users/:id

Example Request:

DELETE http://localhost:3000/users/1

Response:
{
  "message": "User deleted successfully"
}


