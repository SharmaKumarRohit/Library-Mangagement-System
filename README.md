# Library-Mangagement-System (Backend API)

A **RESTful Library Management System API** built using **Node.js, Express, and MongoDB**. This backend application helps manage **users, books, subscriptions, book issuance, and fine calculations** in a structured way .

## Features

- User management
- Book management
- Book issuing
- Subscription plans (Basic, Standard, Premium)
- Automatic fine calculation for late renewals
- MVC architecture for clean code organization
- MongoDB Atlas database integration

## Tech Stack

- **Node.js** – Runtime environment
- **Express.js** – Node.js Framework
- **MongoDB** – NoSQL Database
- **Mongoose** – MongoDB ODM (Object Data Modeling)
- **dotenv** – Environment variable management
- **nodemon** – Server auto-reload

## Project Structure (MVC)

    Library-Management-System
    │
    ├── controllers # Logic of server
    ├── dtos # Only book dto
    ├── models # MongoDB schemas
    ├── routes # API routes
    ├── .gitignore # Ignoring unnecessary files and folders
    ├── db.js # Database connection
    ├── package.json
    └── server.js # main file

### API Endpoints

#### Users

`/users`

- **GET** – Fetch all users
- **POST** – Add a new user

`/users/{id}`

- **GET** – Get user by ID
- **PUT** – Update user details
- **DELETE** - Delete user

`/users/subscription-details/{id}`

- **GET** – Fetch subscription details
  - Subscription start date
  - Validity
  - Fine

---

#### Books

`/books`

- **GET** – Fetch all books
- **POST** – Add a new book

`/books/{id}`

- **GET** – Get book by ID
- **PUT** – Update book details
- **DELETE** - Delete book

`/books/issued/for-users`

- **GET** – Get all issued books

<hr />

### Subscription Plans

| Plan     | Duration  |
| -------- | --------- |
| Basic    | 3 Months  |
| Standard | 6 Months  |
| Premium  | 12 Months |

#### Fine Rules

- Missed renewal → ₹100 fine
- Missed subscription → ₹100 fine
- Missed both → ₹200 fine

<hr />

### Usage & Installation

```bash
npm init
npm install express mongoose dotenv
npm install nodemon --save-dev
```

#### Run the Server

```bash
npm run dev
```

#### Install Dependencies

```bash
npm install
```

<hr />

### Database connection

You can use **MongoDB Atlas** or **Local MongoDB**. Add these variables in your `.env` file:

```bash
PORT=8081
MONGO_URL=mongodb+srv://<db_user>:<db_password>@cluster0.wgvhanf.mongodb.net/LMS
MONGO_URL_LOCAL=mongodb://127.0.0.1:27017/
```

<hr />

### MVC Architecture

- **Model (M)** – Define MongoDB schema and structure
- **View (V)** – Frontend
- **Controller (C)** – Handles request and responses

<hr />

### DTO (Data Transfer Object)

DTOs are used to transfer structured data between layers, ensuring:

- Data consistency
- Security
- Clean API responses

<hr />

#### License

This project is open-source and available for learning and educational purposes.
