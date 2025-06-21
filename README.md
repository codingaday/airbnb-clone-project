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

## Technology Stack

## Category | Technology

Backend Framework | Django
REST API | Django REST Framework
GraphQL API | GraphQL
Database | PostgreSQL
Caching | Redis
Task Queue | Celery
Containerization | Docker
Deployment | CI/CD Pipelines
API Documentation | OpenAPI Standard

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
