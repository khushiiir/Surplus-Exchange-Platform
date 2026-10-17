# Surplus Exchange Platform

A **B2B surplus inventory marketplace** built with React and Spring Boot that connects businesses looking to sell excess inventory with buyers seeking cost-effective products. The platform helps businesses recover value from surplus stock, reduce storage costs, and minimize inventory waste.

## Overview

Businesses often hold excess, unused, overstocked, or leftover inventory that ties up capital and warehouse space. The Surplus Exchange Platform provides a centralized marketplace where sellers can list surplus products and buyers can discover and purchase them.

Unlike a traditional e-commerce application, the platform focuses on **business-to-business inventory redistribution and value recovery**.

## Key Features

### Authentication & Authorization
- User registration and login.
- JWT-based authentication.
- Role-based access control for buyers, sellers, and administrators.
- Protected routes and role-specific functionality.

### Product Management
- Create, update, view, and manage surplus product listings.
- Browse available products and product categories.
- View detailed product information.
- Upload and manage product images.
- Support for seller-owned product management.

### Buyer Functionality
- Browse and discover surplus inventory.
- View product details and pricing.
- Add products to the shopping cart.
- Proceed through checkout and order workflows.
- View and manage orders.

### Seller Functionality
- List excess and unused inventory.
- Manage product details, pricing, and images.
- Track product listings and order-related activities.
- Support seller verification workflows.

### Admin Dashboard
- Manage platform users.
- Review seller and product verification requests.
- Monitor orders.
- Access dashboard statistics and reports.

### Additional Capabilities
- Responsive React-based user interface.
- RESTful API integration.
- Centralized state management with Redux.
- MySQL database persistence.
- Cloudinary-based product image storage.

> **Note:** Payment gateway integration, shipping integration, and advanced analytics should be listed as implemented features only after their end-to-end functionality has been verified.

## Technology Stack

| Layer | Technologies |
|---|---|
| Frontend | React.js, JavaScript |
| UI & Styling | Tailwind CSS, Material UI |
| Routing | React Router |
| State Management | Redux |
| HTTP Client | Axios, Fetch API |
| Backend | Java, Spring Boot |
| Security | Spring Security, JWT |
| Database | MySQL |
| ORM | Spring Data JPA, Hibernate |
| Image Storage | Cloudinary |
| Build Tool | Maven |
| Development Tools | Git, GitHub |

## System Architecture

The application follows a layered architecture in which the React frontend communicates with the Spring Boot backend through REST APIs.

```text
                    User
                     |
                     v
          +----------------------+
          |    React Frontend    |
          |  React Router / Redux|
          +----------------------+
                     |
                     v
          +----------------------+
          |   REST API Layer     |
          | Spring Boot Security |
          +----------------------+
                     |
                     v
          +----------------------+
          |    Service Layer     |
          |    Business Logic    |
          +----------------------+
                     |
                     v
          +----------------------+
          |   Repository Layer   |
          |    Spring Data JPA   |
          +----------------------+
                     |
                     v
          +----------------------+
          |        MySQL         |
          +----------------------+

          Product Images
                 |
                 v
             Cloudinary
```

### Request Flow

1. Users interact with the React frontend.
2. The frontend sends HTTP requests to the backend REST APIs.
3. Spring Security validates authentication and authorization where required.
4. Controllers delegate business operations to service classes.
5. Repository classes interact with the MySQL database.
6. The backend returns responses to the frontend, which updates the user interface.

## Security

The application uses JWT-based authentication and role-based authorization to control access to protected resources.

- **JWT Authentication:** Tokens are used to authenticate authorized API requests.
- **Role-Based Access Control:** Access to features is determined by user roles.
- **Protected Endpoints:** Restricted resources require appropriate authentication and authorization.
- **Seller Ownership:** Seller operations should verify ownership of the relevant product listings.
- **Admin Authorization:** Administrative endpoints should be accessible only to authorized administrators.
- **Credential Management:** Database passwords, JWT secrets, and API credentials should be stored in environment variables rather than committed to source control.

## Database

MySQL stores the application's persistent business data, including user accounts, product listings, and order-related records.

Spring Data JPA and Hibernate provide object-relational mapping between Java entities and database tables.

Cloudinary is used to store product images, while image metadata and product associations are maintained by the application.

## Future Enhancements

- Real-time price negotiation between buyers and sellers.
- Integrated shipping and logistics services.
- Payment gateway integration.
- Advanced sales and inventory analytics.
- Product recommendations and intelligent surplus matching.
- Notifications for offers, orders, and verification updates.
- Production deployment with monitoring and CI/CD automation.

## Business Impact

The platform aims to help businesses:

- **Recover value** from unsold inventory.
- **Reduce storage costs** associated with excess stock.
- **Expand business reach** by connecting sellers with potential B2B buyers.
- **Improve inventory utilization** through surplus redistribution.
- **Reduce material waste** by extending the useful life of existing inventory.

If you find this project useful, consider giving the repository a star.

