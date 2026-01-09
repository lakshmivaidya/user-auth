# User Authentication and Authorization with JWT (Bearer Token)

## Project Description
This project implements user authentication and authorization using **JWT Bearer Tokens** in a **Node.js** application following the **MVC architecture**.  
Users can register, log in, and access protected routes using a valid JWT.

The APIs are fully tested and documented using **Postman**.

---

## Tech Stack
- Node.js
- Express.js
- MongoDB (Mongoose)
- JWT (JSON Web Token)
- Postman (API testing & documentation)

---

## Project Structure (MVC)
├── controllers/
├── middleware/
├── models/
├── routes/
├── config/
├── server.js
├── .env
├── README.md


---

## Installation & Running the Project

### 1. Install Dependencies
```bash
npm install

2. Start the Server
npm run dev


The server will run on:

http://localhost:5000

API Documentation (Postman)

All API endpoints are tested and documented in Postman.

Postman Collection

API Endpoints
1️. Register User

POST http://localhost:5000/api/auth/register

Request Body (JSON):

{
  "username": "testuser",
  "email": "testuser@example.com",
  "password": "Test1234"
}

Success Response:

{
  "message": "User registered successfully"
}

2️. Login User

POST http://localhost:5000/api/auth/login

Request Body (JSON):

{
  "email": "testuser@example.com",
  "password": "Test1234"
}

Success Response:

{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY5NjBlNzhmNDllMmM2YTZmMTRhNjFhMCIsImVtYWlsIjoidGVzdHVzZXJAZXhhbXBsZS5jb20iLCJpYXQiOjE3Njc5NTkzMzQsImV4cCI6MTc2Nzk2MjkzNH0.ebOj3TucNpjMzgcjbU8Xbf-oPnhdISTuDpIwBRUwM3k"
}

3️. Get User Information (Protected Route)

GET http://localhost:5000/api/auth/me

Success Response:

{
    "user": {
        "id": "6960e78f49e2c6a6f14a61a0",
        "email": "testuser@example.com",
        "iat": 1767959334,
        "exp": 1767962934
    }
}
Authentication Flow

User registers using /register

User logs in using /login

JWT token is returned

Token is sent in Authorization header as:

Bearer <token>

Protected routes verify the token using middleware