# 🏡 Airbnb Clone Project

## 📌 Overview

The **Airbnb Clone Project** is a comprehensive, real-world application designed to simulate the development of a scalable booking platform like Airbnb.
It focuses on **backend systems, database design, API development, and application security** while enabling learners to understand **complex architectures, workflows, and team collaboration**.

## 🎯 Project Goals

* Develop a backend system that supports **property listings, user management, booking, and payments**.
* Design and document **database schemas** for scalability and efficiency.
* Secure APIs using **authentication, authorization, and rate limiting**.
* Implement **CI/CD pipelines** for automated testing and deployment.
* Gain experience with **Django, MySQL, GraphQL, and Docker**.

## 👥 Team Roles

* **Backend Developer** – Builds APIs, manages business logic, integrates frontend and backend.
* **Database Administrator (DBA)** – Designs, maintains, and optimizes the database schema and queries.
* **DevOps Engineer** – Handles deployment, CI/CD pipelines, Docker setup, and server monitoring.
* **Security Engineer** – Implements API security, handles authentication & authorization, ensures compliance with best practices.
* **Project Manager** – Coordinates workflows, tracks tasks, and ensures deadlines are met.

## 🛠️ Technology Stack

* **Django** – Python web framework for building RESTful APIs.
* **Django Rest Framework (DRF)** – Simplifies API creation and serialization.
* **MySQL** – Relational database for persistent storage.
* **GraphQL** – Provides flexible and efficient querying for frontend clients.
* **Docker** – Containerization for easy deployment and consistency across environments.
* **GitHub Actions** – Automates CI/CD pipelines for testing and deployment.
* **Celery + RabbitMQ** – Task queue for background jobs and async processing.

## 🗄️ Database Design

### Key Entities:

1. **Users**

   * `user_id` (Primary Key)
   * `name`
   * `email`
   * `password_hash`
   * `role` (guest, host, admin)

2. **Properties**

   * `property_id` (Primary Key)
   * `host_id` (FK → Users)
   * `title`
   * `description`
   * `price_per_night`

3. **Bookings**

   * `booking_id` (Primary Key)
   * `property_id` (FK → Properties)
   * `guest_id` (FK → Users)
   * `start_date`
   * `end_date`

4. **Reviews**

   * `review_id` (Primary Key)
   * `booking_id` (FK → Bookings)
   * `rating`
   * `comment`

5. **Payments**

   * `payment_id` (Primary Key)
   * `booking_id` (FK → Bookings)
   * `amount`
   * `status`

🔗 Relationships:

* A **User** can host multiple **Properties**.
* A **Property** can have multiple **Bookings**.
* A **Booking** belongs to one **Property** and one **User** (guest).
* A **Review** is tied to a **Booking**.
* A **Payment** is linked to a **Booking**.

## ⚙️ Feature Breakdown

* **User Management** – Registration, login, profile management, roles (guest/host/admin).
* **Property Management** – Hosts can add, update, and delete property listings.
* **Booking System** – Guests can search, book, cancel, and manage stays.
* **Payment Processing** – Secure transactions with payment gateway integration.
* **Review System** – Guests can leave reviews and ratings after bookings.
* **Notifications** – Email and in-app alerts for bookings, cancellations, and confirmations.
* **Admin Dashboard** – Admins can oversee all users, bookings, and properties.

## 🔐 API Security

* **Authentication** – JWT-based authentication for all API requests.
* **Authorization** – Role-based access control (guests, hosts, admins).
* **Rate Limiting** – Protects against abuse and DoS attacks.
* **Data Validation** – Prevents SQL injection, XSS, and invalid inputs.
* **Secure Payments** – Encrypted payment data storage and integration with gateways.

## 🚀 CI/CD Pipeline

* **Continuous Integration (CI):** Automatically run tests on every push using GitHub Actions.
* **Continuous Deployment (CD):** Deploy containerized services to production using Docker & GitHub Actions.
* **Automated Testing:** Unit tests and integration tests run on PRs.
* **Monitoring & Logging:** Logs and metrics collected for system health checks.
