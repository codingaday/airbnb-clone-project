# Airbnb Clone Project

This project is a backend system that mimics core features of Airbnb, such as user management, property listings, bookings, payments, and reviews. It is built using scalable technologies and optimized for performance and maintainability.

# Feature Breakdown

- **User Management**  
  Handles registration, login, and profile management for users. This ensures both guests and hosts can securely access and manage their accounts.

- **Property Management**  
  Allows hosts to create, update, and manage property listings. Properties include details like title, location, price, and description to attract potential guests.

- **Booking System**  
  Enables users to reserve available properties for specific dates. This feature tracks check-in/check-out information and prevents double bookings.

- **Payment Processing**  
  Manages transactions for bookings through secure payment gateways. It ensures payments are recorded, verified, and linked to booking records.

- **Review System**  
  Lets users leave feedback and ratings after a stay. Reviews help maintain quality and build trust between hosts and guests.

- **API Documentation**  
  Provides clear REST and GraphQL documentation using OpenAPI standards. This helps frontend developers and third parties integrate with the backend easily.

- **Database Optimization**  
  Uses indexing and caching to improve performance. This ensures quick response times for searches, bookings, and listing retrievals.

- **Asynchronous Tasks (Celery)**  
  Manages background operations like sending emails or processing payments. This keeps the main app responsive and efficient.

- **Containerized Deployment (Docker)**  
  Ensures consistent environments across development and production. Helps scale and deploy the backend with minimal friction.

# Technology Stack

- **Django**  
  A high-level Python web framework used to build and manage the backend logic and models.

- **Django REST Framework (DRF)**  
  A powerful toolkit for building Web APIs, used to expose CRUD functionality through RESTful endpoints.

- **GraphQL**  
  Enables flexible and efficient data querying for clients, minimizing over-fetching and under-fetching.

- **PostgreSQL**  
  A robust and scalable relational database system used to store structured application data.

- **Redis**  
  An in-memory data store used for caching and session management to boost performance.

- **Celery**  
  Handles asynchronous tasks like sending emails and processing background jobs (e.g., payments).

- **Docker**  
  Containerizes the application for consistent environments during development, testing, and deployment.

- **CI/CD Pipelines**  
  Automates testing and deployment to ensure smooth, reliable, and fast delivery of code updates.

## REST API Endpoints

### Users

- `GET /users/` — List users
- `POST /users/` — Create user
- `GET /users/{user_id}/` — Retrieve user
- `PUT /users/{user_id}/` — Update user
- `DELETE /users/{user_id}/` — Delete user

### Properties

- `GET /properties/` — List properties
- `POST /properties/` — Add property
- `GET /properties/{property_id}/` — Get property
- `PUT /properties/{property_id}/` — Update property
- `DELETE /properties/{property_id}/` — Delete property

### Bookings

- `GET /bookings/` — List bookings
- `POST /bookings/` — Create booking
- `GET /bookings/{booking_id}/` — Get booking
- `PUT /bookings/{booking_id}/` — Update booking
- `DELETE /bookings/{booking_id}/` — Cancel booking

### Payments

- `POST /payments/` — Process payment

### Reviews

- `GET /reviews/` — List reviews
- `POST /reviews/` — Add review
- `GET /reviews/{review_id}/` — View review
- `PUT /reviews/{review_id}/` — Edit review
- `DELETE /reviews/{review_id}/` — Delete review

# Database Design

- **Users**

  - `id`: Unique identifier
  - `name`: Full name of the user
  - `email`: Used for login and communication
  - `password`: Hashed password
  - `role`: Host or guest

- **Properties**

  - `id`: Unique identifier
  - `title`: Name of the property
  - `description`: Property details
  - `location`: Address or city
  - `owner_id`: References the user (host) who owns the property

- **Bookings**

  - `id`: Unique identifier
  - `property_id`: References the booked property
  - `user_id`: References the guest who made the booking
  - `check_in`: Start date of stay
  - `check_out`: End date of stay

- **Reviews**

  - `id`: Unique identifier
  - `property_id`: References the property being reviewed
  - `user_id`: References the user who wrote the review
  - `rating`: Numeric score (e.g., 1–5)
  - `comment`: Written feedback

- **Payments**
  - `id`: Unique identifier
  - `booking_id`: References the related booking
  - `amount`: Payment total
  - `payment_method`: E.g., card, PayPal
  - `status`: E.g., completed, pending, failed

## Entity Relationships

- A **User** can own multiple **Properties**
- A **Property** can have multiple **Bookings**
- A **Booking** is made by one **User** and linked to one **Property**
- A **User** can leave multiple **Reviews**, each tied to one **Property**
- A **Payment** is linked to one **Booking**

# API Security

- **Authentication**  
  The system will use token-based authentication (e.g., JWT or DRF TokenAuth) to ensure only verified users can access protected endpoints. This helps prevent unauthorized access to user accounts and personal data.

- **Authorization**  
  Role-based access control (RBAC) will be applied to restrict what users can do based on their role (e.g., guest, host, admin). This ensures users can only perform actions allowed for their access level, such as editing only their own properties or bookings.

- **Rate Limiting**  
  Limits will be placed on API requests (e.g., per minute/hour) to prevent abuse, brute-force attacks, and denial-of-service (DoS) attempts. This keeps the system stable and fair for all users.

- **Data Validation and Input Sanitization**  
  All user input will be validated and sanitized to prevent injection attacks such as SQL injection or XSS. This protects the backend and users from malicious data.

- **Secure Payment Processing**  
  Payments will be handled through trusted third-party providers (e.g., Stripe or PayPal) using encrypted connections. This ensures sensitive financial data is never directly exposed or stored on the server.

- **HTTPS Enforcement**  
  All traffic will be encrypted using HTTPS to protect data in transit, preventing man-in-the-middle attacks.

## Why Security Matters

- **Protecting User Data**  
  Users entrust the platform with personal and financial information. Securing this data builds trust and meets compliance standards.

- **Securing Transactions**  
  Payment fraud or tampering can lead to major financial loss. Security measures ensure that all transactions are legitimate and traceable.

- **Maintaining Platform Integrity**  
  Authorization and rate limiting prevent users from exploiting the system, which protects both the business and its users.

- **Preventing Downtime and Abuse**  
  Security measures help guard the API against attacks that can cause outages or degrade performance for legitimate users.

# Team Roles

- **Product Owner**  
  Defines the project vision, manages features and priorities.

- **Business Analyst**  
  Translates business needs into clear technical requirements.

- **Project Manager / Scrum Master**  
  Keeps the team on track, manages deadlines, and removes blockers.

- **UI/UX Designer**  
  Designs user-friendly interfaces and ensures a smooth user experience.

- **Software Architect**  
  Plans the system structure and ensures scalability and best practices.

- **Backend Developer**  
  Builds API endpoints, handles business logic, and backend services.

- **Frontend/Mobile Developer**  
  (Future scope) Builds user interfaces and connects them to APIs.

- **Database Administrator**  
  Designs and optimizes the database for performance and data integrity.

- **DevOps Engineer**  
  Sets up CI/CD pipelines, manages deployments, and system monitoring.

- **QA Engineer**  
  Tests features, finds bugs, and ensures the product meets quality standards.

- **Test Automation Engineer**  
  Writes automated tests to speed up testing and catch issues early.

## API Docs

- OpenAPI for REST endpoints
- GraphQL playground for querying the backend
