# airbnb-clone-project

## Overview

This project is a clone of the popular AirBnB platform, designed to simulate its core functionalities including property listings, user authentication, bookings, and reviews. The goal is to develop a fully functional web application from the ground up, applying best practices in software development.

## Project Goals

-   Build a scalable web application
-   Practice full-stack development (front-end, back-end, database)
-   Implement RESTful APIs
-   Create a responsive UI mimicking AirBnB’s design
-   Manage users, listings, reservations, and reviews

## 🛠 Tech Stack

### Front-End:

-   HTML, CSS, JavaScript
-   React (or optional: plain JS for MVP)

### Back-End:

-   Python
-   Flask (or Django depending on version)

### Database:

-   MySQL / PostgreSQL / SQLite

### Tools & Platforms:

-   Git & GitHub
-   Docker (optional)
-   REST API
-   Unit Testing (Unittest / Pytest)

---

## 🚧 Status

Project initialization in progress...

"Team Roles"

Below is a list of key team roles involved in the AirBnB Clone project and their responsibilities:

# Project Manager (PM)

Oversees the entire project from start to finish.

Defines project scope, sets milestones, and ensures deadlines are met.

Acts as a bridge between developers, stakeholders, and designers.

# Backend Developer

Implements the business logic and server-side functionality.

Builds RESTful APIs to handle requests and responses.

Ensures application scalability, security, and performance.

# Frontend Developer

Creates the user interface and implements the design.

Works closely with designers to convert mockups into interactive pages.

Integrates the frontend with backend APIs for dynamic content.

# Database Administrator (DBA)

Designs, implements, and manages the database schema.

Ensures data integrity, backups, and performance optimization.

Writes complex queries and manages access controls.

# QA Engineer (Tester)

Tests the application manually and/or automatically to identify bugs.

Ensures that new features do not break existing functionality (regression testing).

Verifies application performance, usability, and compliance.

# UI/UX Designer

Designs wireframes, mockups, and the overall look and feel of the app.

Focuses on usability and user experience to make the app intuitive.

Works closely with frontend developers to ensure design consistency.

# DevOps Engineer (optional/advanced)

Sets up continuous integration and deployment (CI/CD) pipelines.

Manages cloud services, containerization (e.g., Docker), and deployment.

Monitors application uptime and performance in production.

---

## Technology Stack

This project uses the following technologies to build a scalable, maintainable, and feature-rich AirBnB clone:

### Backend

-   **Django**: A high-level Python web framework that encourages rapid development and clean, pragmatic design. It handles routing, business logic, authentication, and RESTful API creation.
-   **GraphQL** _(optional)_: A flexible query language for APIs. Used to allow clients to request exactly the data they need and nothing more, improving performance and developer experience.

### Database

-   **PostgreSQL**: A powerful, open-source relational database system. It stores user data, property listings, bookings, reviews, etc., and works seamlessly with Django’s ORM.

### Frontend

-   **React** _(or plain JavaScript)_: A JavaScript library for building interactive UIs. It allows us to create reusable components and manage complex frontend states.
-   **HTML/CSS**: Core technologies for structuring and styling web pages.

### Dev Tools & Infrastructure

-   **Docker** _(optional/advanced)_: Used to containerize the application, ensuring consistent environments across development, testing, and production.
-   **Git**: Version control system to track changes in code and collaborate with team members.
-   **GitHub**: Hosting platform for version control and collaboration.

### Testing

-   **Pytest** or **Unittest**: Frameworks for writing and running automated tests to ensure code correctness and stability.

---

---

---

## Database Design

The application uses a relational database to manage users, property listings, bookings, reviews, and payments. Below are the core entities and their relationships.

### Users

Represents users of the platform, both hosts and guests.

**Fields:**

-   `id` (Primary Key)
-   `name`
-   `email` (unique)
-   `password_hash`
-   `role` (host or guest)

**Relationships:**

-   A user can **list multiple properties**
-   A user can **make multiple bookings**
-   A user can **write multiple reviews**

---

### Properties

Represents property listings created by hosts.

**Fields:**

-   `id` (Primary Key)
-   `owner_id` (Foreign Key to Users)
-   `title`
-   `description`
-   `location`
-   `price_per_night`

**Relationships:**

-   A property **belongs to one user** (host)
-   A property can have **many bookings**
-   A property can have **many reviews**

---

### Bookings

Represents reservations made by users for properties.

**Fields:**

-   `id` (Primary Key)
-   `property_id` (Foreign Key to Properties)
-   `user_id` (Foreign Key to Users)
-   `start_date`
-   `end_date`
-   `status` (e.g., pending, confirmed, canceled)

**Relationships:**

-   A booking **belongs to one user**
-   A booking **belongs to one property**

---

### Reviews

Users can review properties they have stayed in.

**Fields:**

-   `id` (Primary Key)
-   `user_id` (Foreign Key to Users)
-   `property_id` (Foreign Key to Properties)
-   `rating` (1–5)
-   `comment`

**Relationships:**

-   A review **belongs to one user**
-   A review **belongs to one property**

---

### Payments

Tracks transactions made for bookings.

**Fields:**

-   `id` (Primary Key)
-   `booking_id` (Foreign Key to Bookings)
-   `amount`
-   `payment_method` (e.g., credit card, PayPal)
-   `status` (e.g., paid, refunded)

**Relationships:**

-   A payment **belongs to one booking**

---

### Entity Relationship Summary

-   **User 1 : N Properties**
-   **User 1 : N Bookings**
-   **Property 1 : N Bookings**
-   **Property 1 : N Reviews**
-   **User 1 : N Reviews**
-   **Booking 1 : 1 Payment**

---
