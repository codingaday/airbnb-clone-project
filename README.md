#Airbnb Clone Project

This project is a backend system that mimics core features of Airbnb, such as user management, property listings, bookings, payments, and reviews. It is built using scalable technologies and optimized for performance and maintainability.



##Project Objectives

- **User Management**: Secure user registration, authentication, and profile handling.
- **Property Management**: Full CRUD for property listings.
- **Booking System**: Enable users to book properties and manage reservations.
- **Payment Processing**: Integrate and manage booking payments.
- **Review System**: Allow users to leave feedback on properties.
- **Data Optimization**: Use caching and indexing for fast, efficient queries.


##Tech Stack

 Category          |        Technology 
---------------------------------------
 Backend Framework |        Django 
 REST API          |        Django REST Framework 
 GraphQL API       |        Graphene / GraphQL 
 Database          |        PostgreSQL 
 Caching           |        Redis 
 Task Queue        |        Celery 
 Containerization  |        Docker 
 Deployment        |        CI/CD Pipelines 
 API Documentation |        OpenAPI Standard 



##REST API Endpoints

###Users
- `GET /users/` — List users  
- `POST /users/` — Create user  
- `GET /users/{user_id}/` — Retrieve user  
- `PUT /users/{user_id}/` — Update user  
- `DELETE /users/{user_id}/` — Delete user  

###Properties
- `GET /properties/` — List properties  
- `POST /properties/` — Add property  
- `GET /properties/{property_id}/` — Get property  
- `PUT /properties/{property_id}/` — Update property  
- `DELETE /properties/{property_id}/` — Delete property  

###Bookings
- `GET /bookings/` — List bookings  
- `POST /bookings/` — Create booking  
- `GET /bookings/{booking_id}/` — Get booking  
- `PUT /bookings/{booking_id}/` — Update booking  
- `DELETE /bookings/{booking_id}/` — Cancel booking  

###Payments
- `POST /payments/` — Process payment  

###Reviews
- `GET /reviews/` — List reviews  
- `POST /reviews/` — Add review  
- `GET /reviews/{review_id}/` — View review  
- `PUT /reviews/{review_id}/` — Edit review  
- `DELETE /reviews/{review_id}/` — Delete review  


##Roles in the Team

- **Backend Developer** – API development & business logic
- **Database Admin** – Schema design & performance
- **DevOps Engineer** – CI/CD, containerization, monitoring
- **QA Engineer** – Test coverage & quality control



##API Docs

- OpenAPI for REST endpoints
- GraphQL playground for querying the backend






