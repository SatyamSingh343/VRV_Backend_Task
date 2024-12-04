# 🔐 VRV Security RBAC Backend Assignment

Welcome to the *VRV Security RBAC Backend Assignment*!  
This project implements a *Role-Based Access Control (RBAC)* system for managing user roles and permissions with API security at its core. Built using modern development practices, it is designed for scalability, security, and ease of use. 🎯

---


🚀 How to Run
Clone the repository:

bash
Copy code
git clone https://github.com/Abhi96k/VRV_Security_RBAC_Backend_Assignment-main.git  
Navigate to the project directory:

markdown
bash
cd VRV_Security_RBAC_Backend_Assignment-main

Install dependencies:

bash
npm install

Create a `.env` file in the root directory and configure the environment variables.

Start the server:

bash
npm start

Access the application at `http://localhost:<PORT>`


## 🌟 Features

### 🔒 *Authentication and Authorization*

- *Secure Password Storage*: User passwords are hashed using bcryptjs for enhanced security.
- *JWT (JSON Web Tokens)*: Supports stateless authentication for secure user sessions.
- *Access and Refresh Tokens*: Ensures session security and persistence with refresh capabilities.
- *HTTP-Only Cookies*: Safeguards tokens against cross-site scripting (XSS) attacks.

### 👥 *Role-Based Access Control (RBAC)*

- Fine-grained access based on user roles:
  - *User*: General access to create and view personal content.
  - *Moderator*: Privileges to review and manage content.
  - *Admin*: Full administrative control over the system, including user management and logs.

### 📊 *Database Integration*

- MongoDB integration using Mongoose for robust and efficient data storage.
- Scalable schema design to handle roles, permissions, and user actions seamlessly.

### 🛡 *API Security*

- *Middleware Validation*: Enforces authentication and authorization for all API endpoints.
- *Data Sanitization*: Prevents injection attacks by validating and sanitizing user inputs.
- *Rate Limiting*: Protects against brute force attacks by limiting repeated requests from the same IP.
- *CORS Configuration*: Ensures secure API consumption from trusted origins.

### ⚙ *Backend Architecture*

- Built using *Node.js* and *Express.js*, optimized for performance.
- Modular structure for easy code readability, maintainability, and scalability.
- Pre-configured development and production environments for seamless deployment.

### 🛠 *Developer-Friendly Features*

- Detailed error handling and logging for streamlined debugging.
- *Prettier* and *ESLint* integrated for consistent code formatting and linting.
- Environment-based configurations for easier deployment in development, staging, or production.

### 📑 *Comprehensive Documentation*

- *Postman API Collection*: Preconfigured API collection for quick testing and integration.
- Detailed API documentation with request/response samples for all endpoints.
- Well-commented codebase for smooth onboarding and extensibility.

### 🔄 *Testing and Monitoring*

- End-to-end API tests using *Jest* and *Supertest* for quality assurance.
- Integrated logging with *Winston* for tracking application and user activities.

### 🚀 *Performance Optimization*

- Optimized database queries with indexes for faster retrievals.
- Asynchronous and non-blocking operations to handle concurrent API requests efficiently.
- Ready for horizontal scaling to support increasing user loads.

---

## 🛠 Prerequisites

To get started, ensure you have the following installed:

- *Node.js*: v14.x or higher
- *npm*: v6.x or higher
- *MongoDB*: A running MongoDB instance (local or cloud-based like Atlas).
- *Postman*: For testing APIs.
- *Dependencies*: Ensure these packages are installed:
  - bcrypt (v5.1.1)
  - cookie-parser (v1.4.7)
  - dotenv (v16.4.5)
  - express (v4.21.1)
  - jsonwebtoken (v9.0.2)
  - mongoose (v8.8.3)
  - cors, express-rate-limit, helmet

---

## 📋 Environment Variables

Add the following environment variables to a .env file in the root directory:

`env
PORT=your_server_port
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
JWT_ACCESS_EXPIRY=15m
JWT_REFRESH_EXPIRY=7d
RATE_LIMIT_MAX=100
CORS_ORIGIN=http://localhost:3000


## 🛠 Prerequisites

- **Node.js**: v14.x or higher
- **npm**: v6.x or higher
- **MongoDB**: A running instance of MongoDB (local or cloud-based like Atlas)
- **Postman**: For API testing
- **Dependencies**: Ensure the following packages are installed:
  - `bcrypt` (v5.1.1)
  - `cookie-parser` (v1.4.7)
  - `dotenv` (v16.4.5)
  - `express` (v4.21.1)
  - `jsonwebtoken` (v9.0.2)
  - `mongoose` (v8.8.3)

---



## 🚀 How to Run

1. Clone the repository: `git clone https://github.com/Wizard0880/VRV_Security_RBAC_Backend_Assignment.git`
2. Navigate to the project directory: `cd VRV_Security_RBAC_Backend_Assignment`
3. Install dependencies: `npm install`
4. Create a `.env` file in the root directory and add the required environment variables as mentioned above.
5. Start the server: `npm start`

---

## 📂 Project Structure

- **routes/auth.routes.js**
  Contains the following endpoints:
  - `POST /register` - For user registration.
  - `POST /login` - For user login.
  - `POST /logout` - For logging out users.
  - `POST /create-content` - For users to create new content.

- **routes/admin.routes.js**
  Contains the following endpoints:
  - `GET /logs` - For admins to view application logs.
  - `PUT /update-user-status` - For admins to update the status of users.
  - `DELETE /delete-user/:userId` - For admins to delete specific users by ID.

- **routes/moderator.routes.js**
  Contains the following endpoints:
  - `GET /pending-content` - For moderators to review pending content.
  - `POST /feedback` - For moderators to provide feedback.

---

## 🔎 Testing the API

Use **Postman** or similar API testing tools to test the endpoints.

1. **User Registration and Authentication**
   - Register a new user:
     Method: `POST`
     Endpoint: `/register`
     Body:
     json
     {
       "fullname": "exampleUser",
       "email":"example@gmail.com",
       "password": "examplePassword",
       "role": "User"
     }
     
   - Log in:
     Method: `POST`
     Endpoint: `/login`
     Body:
     json
     {
       "email": "example@gmail.com",
       "password": "examplePassword"
     }
     
   - Log out:
     Method: `POST`
     Endpoint: `/logout`

2. **Create Content**
   - Create new content:
     Method: `POST`
     Endpoint: `/create-content`
     Headers:
     
     Authorization: Bearer <access_token>
     
     Body:
     json
     {
       "title": "My New Content",
       "body": "Detailed description of the content.",
       "createdBy": "ID of the user creating the content"
     }
     
     Expected Response:
     json
     {
       "message": "Content created successfully!",
       "contentId": "content123"
     }
     

3. **Admin Endpoints**
   - View logs:
     Method: `GET`
     Endpoint: `/logs`
   - Update user status:
     Method: `PUT`
     Endpoint: `/update-user-status`
     Body:
     json
     {
       "userId": "user123",
       "status": "Active"
     }
     
   - Delete a user:
     Method: `DELETE`
     Endpoint: `/delete-user/:userId`

4. **Moderator Endpoints**
   - View pending content:
     Method: `GET`
     Endpoint: `/pending-content`
   - Provide feedback:
     Method: `POST`
     Endpoint: `/feedback`
     Body:
     json
     {
       "contentId": "content123",
       "feedback": "Looks good!"
     }
     

---

## **API Flow**
![API-Flow](https://github.com/user-attachments/assets/ad38bcf9-85eb-401a-8a5c-ac527b315af6)

---
## 🛡 Security Features

- Passwords are securely hashed using `bcryptjs`.
- JWT-based authentication with access and refresh tokens ensures session security.
- HTTP-only cookies protect against XSS attacks.
- Role-based access control restricts users to authorized actions only.

---

## 📜 License

This project is licensed under the MIT License.
`

### Planned Features:

1. *Audit Logs*

   - Track and record all user actions and administrative operations for accountability and transparency.

2. *Custom Permissions*

   - Extend the RBAC system to support user-specific custom permissions for granular access control.

3. *Two-Factor Authentication (2FA)*

   - Strengthen security by implementing 2FA during login for additional protection.

4. *WebSocket Support*

   - Enable real-time notifications for key actions, such as content approval or status updates for users.

5. *Cache Layer*
   - Integrate *Redis* or *Memcached* to cache frequently accessed data and reduce database load.

VRV_Security_RBAC_Backend_Assignment/  
├── controllers/ # Contains controller logic for handling requests  
├── middlewares/ # Custom middleware for authentication and validation  
├── models/ # Mongoose schemas for database entities  
├── routes/ # Defines API routes for users, admins, and moderators  
├── utils/ # Utility functions for reusable logic  
├── .env # Environment variable configuration  
├── app.js # Main application entry point  
├── package.json # Project metadata and dependencies
