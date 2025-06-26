# Airbnb Clone Project - StayBackend

## Overview
This is a backend implementation of an Airbnb-like booking platform. The goal is to build a robust, scalable system that handles users, listings, bookings, payments, and more, using modern backend technologies and best practices.

## Project Goals
- Build a real-world backend application using Django
- Practice relational database modeling with MySQL
- Implement RESTful APIs with proper security
- Set up CI/CD for continuous deployment
- Learn collaborative team development with GitHub

## Team Roles

A successful software project requires a well-defined team structure with clear responsibilities. Below are the key roles involved in the Airbnb Clone backend project:

### 👨‍💻 Backend Developer
Responsible for writing the server-side application logic. In this project, they build APIs using Django, manage user authentication, handle requests and responses, and ensure business logic is implemented correctly.

### 🧠 Database Administrator (DBA)
Designs and maintains the project's relational database. They define data schemas, relationships, indexes, and ensure data integrity and security using MySQL.

### 🧪 QA Engineer
Ensures the application meets quality standards by writing and executing test cases. They focus on identifying bugs and verifying that all features perform as intended, including API testing with tools like Postman or automated test frameworks.

### 🛡️ DevOps Engineer
Handles CI/CD pipeline setup and infrastructure management. They automate testing and deployment using tools like GitHub Actions and Docker, ensuring consistent and smooth delivery of updates.

### 📝 Technical Writer / Documentation Specialist
Responsible for writing clear, concise, and accurate project documentation. This includes the README, API docs, database schemas, and team contributions.

### 🧭 Project Manager (PM)
Oversees project planning, task assignment, and timeline management. The PM ensures that the team is aligned with the goals and delivers on time while coordinating communication and workflow.

### 🧑‍🎨 UI/UX Designer *(optional in backend-focused projects)*
While primarily frontend, this role may be involved in API contracts and ensuring backend endpoints align with frontend expectations, even if not actively coding in this phase.


## Technology Stack
- Python (Django Framework)
- Postgresql (Relational Database)
- Docker (Containerization)
- Git & GitHub (Version Control & Collaboration)
- GitHub Actions (CI/CD)
- Postman (API Testing)

## Database Design

This project uses **PostgreSQL** as the relational database system. The database is designed to efficiently manage users, property listings, bookings, reviews, and payments while maintaining data integrity and scalability.

### 🧑 Users
Stores information about the platform’s users (both guests and hosts).

**Key Fields:**
- `id`: Primary key
- `full_name`: Full name of the user
- `email`: Unique email address
- `password_hash`: Hashed password for authentication
- `role`: Enum (e.g., "host", "guest", "admin")

### 🏠 Properties
Represents listings created by hosts.

**Key Fields:**
- `id`: Primary key
- `host_id`: Foreign key to `Users.id`
- `title`: Property title
- `description`: Detailed description
- `location`: Address or coordinates
- `price_per_night`: Cost per night

### 📅 Bookings
Tracks reservations made by guests.

**Key Fields:**
- `id`: Primary key
- `guest_id`: Foreign key to `Users.id`
- `property_id`: Foreign key to `Properties.id`
- `start_date`: Start of the booking
- `end_date`: End of the booking
- `status`: Enum (e.g., "pending", "confirmed", "cancelled")

### 💬 Reviews
Captures user feedback on properties.

**Key Fields:**
- `id`: Primary key
- `guest_id`: Foreign key to `Users.id`
- `property_id`: Foreign key to `Properties.id`
- `rating`: Integer (1–5)
- `comment`: Optional text field

### 💳 Payments
Handles payment transactions for bookings.

**Key Fields:**
- `id`: Primary key
- `booking_id`: Foreign key to `Bookings.id`
- `amount`: Total payment amount
- `payment_method`: Enum (e.g., "credit_card", "mpesa", "paypal")
- `payment_status`: Enum (e.g., "completed", "failed", "refunded")

---

### 🔗 Entity Relationships

- A **User** can act as a **host** (listing Properties) or a **guest** (making Bookings).
- A **Property** belongs to one **User** (host) but can have many **Bookings** and **Reviews**.
- A **Booking** is associated with one **User** (guest) and one **Property**.
- A **Review** is written by a **User** (guest) for a **Property**.
- A **Payment** is linked to one **Booking**.

## Feature Breakdown

This Airbnb Clone project includes the following core features to simulate the functionality of a real-world property booking platform. Each feature contributes to building a seamless and secure user experience while ensuring data integrity and scalability.

### 👥 User Management
Handles user registration, login, authentication, and role management (host or guest). It ensures that only authorized users can access specific actions, such as listing properties or making bookings.

### 🏠 Property Management
Allows hosts to create, update, and delete property listings. Properties include details like title, description, location, images, and price per night, making them discoverable to guests.

### 📆 Booking System
Enables guests to search for available properties and make reservations. It manages the start and end dates of bookings, prevents date conflicts, and updates booking statuses accordingly.

### 💬 Review System
Allows guests to leave reviews and ratings for properties after their stay. This feedback helps improve host accountability and provides valuable information for other users.

### 💳 Payment Integration
Manages payment processing for bookings, including tracking amounts, payment methods, and statuses. It ensures that transactions are secure and records are maintained for future reference.

### 🛡️ API Security
Implements robust authentication and authorization mechanisms. Ensures user data and transactions are protected through token-based access and secure endpoints.

### 🔄 CI/CD & Deployment
Uses GitHub Actions and Docker to automate testing, integration, and deployment workflows. This ensures consistent development practices, minimizes errors, and accelerates delivery cycles.

