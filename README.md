# User Authentication and Authorization with JWT (Bearer Token)
# Project Description

This project implements user authentication and authorization using JWT Bearer Tokens in a Node.js application following the MVC architecture.
Users can register, log in, and access protected routes using a valid JWT.

# The APIs are fully tested and documented using Postman.

# Tech Stack
- Node.js
- Express.js
- MongoDB (Mongoose)
- JWT (JSON Web Token)

# Postman (API testing & documentation)

Project Structure (MVC)
├── controllers/
├── middleware/
├── models/
├── routes/
├── config/
├── server.js
├── .env
├── README.md

# Installation & Running the Project Locally
1️. Install Dependencies
npm install

2️. Start the Server
npm run dev


# The server will run on:

http://localhost:5000

# Live Deployment (Render)

The project is deployed on Render at the following URL:

https://user-auth-90qw.onrender.com


All API endpoints can be tested using this URL.

# API Documentation (Postman)
1️. Register User

# Local URL:

POST http://localhost:5000/api/auth/register

# Live URL (Render):

POST https://user-auth-90qw.onrender.com/api/auth/register


# Request Body (JSON):

{
  "username": "testuser",
  "email": "testuser@example.com",
  "password": "Test1234"
}


# Success Response:

{
  "message": "User registered successfully"
}


If user already exists:

{
  "message": "User already exists"
}

2️. Login User

# Local URL:

POST http://localhost:5000/api/auth/login


# Live URL (Render):

POST https://user-auth-90qw.onrender.com/api/auth/login


# Request Body (JSON):

{
  "email": "testuser@example.com",
  "password": "Test1234"
}


# Success Response:

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}

3️. Get User Information (Protected Route)

# Local URL:

GET http://localhost:5000/api/auth/me


# Live URL (Render):

GET https://user-auth-90qw.onrender.com/api/auth/me


# Headers:

Authorization: Bearer <JWT_TOKEN>


# Success Response:

{
    "user": {
        "id": "6960e78f49e2c6a6f14a61a0",
        "email": "testuser@example.com",
        "iat": 1767959334,
        "exp": 1767962934
    }
}

# Authentication Flow

- User registers using /register
- User logs in using /login
- JWT token is returned
- Token is sent in the Authorization header as:
    Bearer <token>
- Protected routes verify the token using middleware

# Important Notes:

- Local testing: use http://localhost:5000 URLs.
- Online testing: use https://user-auth-90qw.onrender.com URLs.
- Postman can store the JWT in a variable to simplify testing of protected routes.
- Environment variables (MONGO_URI, JWT_SECRET, PORT) must be set for deployment on Render.