API Documentation
Base URL
http://localhost:3000/api/auth

Endpoints
1. Register User
URL: /register
Method: POST
Headers: Content-Type: application/json
Body:
json



{
  "username": "johndoe",
  "email": "john@example.com",
  "password": "john123"
}
Success Response (201):
json



{
  "message": "User registered successfully"
}
Error Response (400):
json



{
  "message": "User already exists"
}
2. Login User
URL: /login
Method: POST
Headers: Content-Type: application/json
Body:
json



{
  "email": "john@example.com",
  "password": "password123"
}
Success Response (200):
json



{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
Error Response (400):
json



{
  "message": "Invalid credentials"
}
3. Get User Info
URL: /user
Method: GET
Headers:
Content-Type: application/json
Authorization: Bearer <token>
Success Response (200):
json



{
  "_id": "123456789",
  "username": "johndoe",
  "email": "john@example.com",
  "createdAt": "2025-04-03T12:00:00Z"
}
Error Response (401):
json



{
  "message": "Token is not valid"
}
Error Handling
All endpoints include proper error handling with appropriate status codes and messages.

Validation
Registration requires username, valid email, and password (min 6 chars)
Login requires valid email and password
