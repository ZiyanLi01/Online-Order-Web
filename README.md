# Yumi Food - Online Food Ordering Platform

Yumi Food is a full-stack web application that simulates a DoorDash-like food ordering service. This project demonstrates a complete food ordering system with user authentication, restaurant selection, menu browsing, cart management, and order processing.

## Project Demo
https://github.com/user-attachments/assets/22b4a759-e51d-45cc-9535-2299fe1b24d7

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [API Documentation](#api-documentation)
- [Database Schema](#database-schema)
- [Deployment](#deployment)
- [Development](#development)

## Overview

Yumi Food is a comprehensive full-stack project that brings together modern web technologies to create a seamless food ordering experience. The application consists of a React-based frontend for user interaction and a Spring Boot backend for business logic and data management.

## Features

### User Management
- User registration and authentication
- Secure login/logout functionality
- User profile management

### Restaurant and Menu
- Browse available restaurants
- View restaurant menus with detailed item information
- Search and filter menu items

### Shopping Cart
- Add/remove items from cart
- Real-time cart updates
- Cart persistence across sessions

### Order Management
- Complete order checkout process
- Order history tracking
- Order status management

## Technology Stack

### Frontend
- **React 18.2.0** - Modern JavaScript library for building user interfaces
- **Ant Design 4.24.15** - Enterprise-level UI design language and React UI library
- **React Router** - Client-side routing for single-page applications

### Backend
- **Spring Boot 3.0.6** - Java-based framework for building web applications
- **Spring Security** - Authentication and authorization framework
- **Spring Data JDBC** - Data access layer for database operations
- **Caffeine Cache** - High-performance caching library
- **Java 17** - Modern Java runtime

### Database
- **PostgreSQL 15.2** - Advanced open-source relational database
- **Docker Compose** - Container orchestration for database setup

### Development Tools
- **Gradle** - Build automation tool
- **Docker** - Containerization platform
- **Maven Central** - Dependency management

## Project Structure

```
Online-Order-Web/
├── oneline-order-front-end/          # React Frontend Application
│   ├── public/                       # Static assets
│   ├── src/
│   │   ├── components/               # React components
│   │   │   ├── FoodList.js          # Menu display component
│   │   │   ├── LoginForm.js         # User authentication
│   │   │   ├── MyCart.js            # Shopping cart management
│   │   │   └── SignupForm.js        # User registration
│   │   ├── App.js                   # Main application component
│   │   └── utils.js                 # API utility functions
│   └── package.json                 # Frontend dependencies
│
└── OnlineOrder/                      # Spring Boot Backend Application
    ├── src/main/java/com/laioffer/onlineorder/
    │   ├── controller/               # REST API controllers
    │   │   ├── CartController.java   # Cart management APIs
    │   │   ├── CustomerController.java # User management APIs
    │   │   └── MenuController.java   # Menu and restaurant APIs
    │   ├── entity/                   # Database entities
    │   │   ├── CartEntity.java       # Shopping cart entity
    │   │   ├── CustomerEntity.java   # User entity
    │   │   ├── MenuItemEntity.java   # Menu item entity
    │   │   ├── OrderItemEntity.java  # Order item entity
    │   │   └── RestaurantEntity.java # Restaurant entity
    │   ├── model/                    # Data transfer objects
    │   ├── repository/               # Data access layer
    │   ├── service/                  # Business logic layer
    │   └── OnlineOrderApplication.java # Main application class
    ├── src/main/resources/
    │   ├── application.yml           # Application configuration
    │   └── database-init.sql         # Database initialization script
    ├── build.gradle                  # Build configuration
    └── docker-compose.yml            # Database container setup
```

## Getting Started

### Prerequisites
- Java 17 or higher
- Node.js 16 or higher
- Docker and Docker Compose
- PostgreSQL (via Docker)

### Backend Setup

1. **Start the Database**
   ```bash
   cd OnlineOrder
   docker-compose up -d
   ```

2. **Configure Environment Variables**
   Create a `.env` file in the `OnlineOrder` directory:
   ```env
   DATABASE_URL=localhost
   DATABASE_USERNAME=postgres
   DATABASE_PASSWORD=secret
   INIT_DB=always
   ```

3. **Run the Spring Boot Application**
   ```bash
   cd OnlineOrder
   ./gradlew bootRun
   ```
   The backend will be available at `http://localhost:8080`

### Frontend Setup

1. **Install Dependencies**
   ```bash
   cd oneline-order-front-end
   npm install
   ```

2. **Start the Development Server**
   ```bash
   npm start
   ```
   The frontend will be available at `http://localhost:3000`

## API Documentation

### Authentication Endpoints
- `POST /signup` - User registration
- `POST /login` - User authentication

### Restaurant Endpoints
- `GET /restaurants/menu` - Get all restaurants with menu information
- `GET /restaurant/{restaurantId}/menu` - Get menu items for a specific restaurant

### Cart Endpoints
- `POST /cart/add` - Add item to cart
- `GET /cart` - Get current cart contents
- `DELETE /cart/{itemId}` - Remove item from cart

### Customer Endpoints
- `GET /customer/profile` - Get user profile information
- `PUT /customer/profile` - Update user profile

## Database Schema

The application uses PostgreSQL with the following main entities:

- **CustomerEntity** - User account information
- **RestaurantEntity** - Restaurant details
- **MenuItemEntity** - Menu items with pricing
- **CartEntity** - Shopping cart management
- **OrderItemEntity** - Order tracking and history

## Deployment

### Backend Deployment
The Spring Boot application can be deployed using:
```bash
cd OnlineOrder
./gradlew build
java -jar build/libs/onlineorder-0.0.1-SNAPSHOT.jar
```

### Frontend Deployment
Build the React application for production:
```bash
cd oneline-order-front-end
npm run build
```

The built files will be in the `build` directory, ready for deployment to any static hosting service.

## Development

### Code Style
- Frontend: Follow React best practices and use functional components with hooks
- Backend: Follow Spring Boot conventions and use dependency injection
- Database: Use proper indexing and follow normalization principles

### Testing
- Backend tests are located in `OnlineOrder/src/test/java/`
- Frontend tests can be run with `npm test`

### Contributing
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## Reference

This project was initially inspired by the Laioffer bootcamp curriculum. The implementation has been customized and enhanced with additional features and modern development practices.

## License

This project is for educational purposes and demonstration of full-stack development skills. 

