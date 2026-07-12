# EN2H Booking API

A RESTful Booking Management API developed using **NestJS**, **PostgreSQL**, **Prisma ORM**, and **JWT Authentication**.
This project was created as part of the EN2H Backend Engineering Internship Technical Assessment.

The API provides secure user authentication, service management, and booking management features following REST API best practices.

---

# Project Overview

The EN2H Booking API is a backend application that allows users to:

* Register and authenticate users
* Login using JWT authentication
* Create and manage services
* Create and manage bookings
* Store and retrieve data using PostgreSQL database
* Access API documentation using Swagger

The project follows clean architecture principles and NestJS best practices.

---

# Technologies Used

## Backend

* NestJS
* TypeScript
* Node.js

## Database

* PostgreSQL
* Prisma ORM

## Authentication

* JWT (JSON Web Token)
* Passport JWT

## Documentation

* Swagger / OpenAPI

## Validation

* Class Validator
* Class Transformer

---

# Project Structure

```
src
│
├── auth
│   ├── auth.controller.ts
│   ├── auth.service.ts
│   ├── auth.module.ts
│
├── users
│
├── services
│
├── bookings
│
├── prisma
│
├── app.module.ts
└── main.ts


prisma
│
├── schema.prisma
└── migrations
```

---

# Installation Steps

## 1. Clone Repository

```bash
git clone https://github.com/your-username/en2h-booking-api.git
```

Navigate to project folder:

```bash
cd en2h-booking-api
```

---

## 2. Install Dependencies

```bash
npm install
```

---

# Environment Variables

Create a `.env` file in the project root.

Example:

```env
DATABASE_URL="postgresql://username:password@localhost:5432/bookingdb"

JWT_SECRET="your_secret_key"
```

---

# Database Setup

## Create PostgreSQL Database

Create a PostgreSQL database:

```
bookingdb
```

Update your database connection inside `.env`.

---

## Generate Prisma Client

Run:

```bash
npx prisma generate
```

---

# Running Database Migrations

To create database tables:

```bash
npx prisma migrate dev --name init
```

To check database:

```bash
npx prisma studio
```

---

# Running the Application

## Development Mode

```bash
npm run start:dev
```

Application will run:

```
http://localhost:3000
```

---

## Production Build

Build:

```bash
npm run build
```

Run:

```bash
npm run start:prod
```

---

# API Documentation (Swagger)

Swagger documentation is available at:

```
http://localhost:3000/api
```

Available APIs:

## Authentication

### Register User

```
POST /auth/register
```

### Login User

```
POST /auth/login
```

---

## Services

### Create Service

```
POST /services
```

### Get Services

```
GET /services
```

---

## Bookings

### Create Booking

```
POST /bookings
```

### Get Bookings

```
GET /bookings
```

---

# Authentication Flow

1. User registers an account.
2. User logs in.
3. Server generates JWT access token.
4. Token is used to access protected APIs.

Example:

```
Authorization: Bearer <access_token>
```

---

# Database Design

Main entities:

## User

Stores user information and authentication details.

## Service

Stores available services.

## Booking

Stores user booking information.

Relationships:

```
User
 |
 |---- Booking
 |
Service
 |
 |---- Booking
```

---

# Validation and Error Handling

The project uses:

* DTO validation
* Global exception handling
* Meaningful HTTP status codes
* Secure authentication validation

---

# Assumptions Made

* Users must authenticate before accessing protected resources.
* Each booking belongs to a registered user.
* Services are created and managed by authorized users.
* PostgreSQL is used as the primary database.

---

# Future Improvements

Possible future enhancements:

* Admin dashboard
* Payment gateway integration
* Email notifications
* Role-based access control
* Advanced search and filtering
* Unit and integration testing improvements
* Cloud deployment

---

# API Testing

Recommended tools:

* Swagger UI
* Postman

---

# Author

**Savindi Liyanage**

BSc (Hons) Software Engineering Student

---

# License

This project was developed for educational and assessment purposes.
