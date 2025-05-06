# EasyStay - Hotel Booking System

## Overview
EasyStay is a comprehensive hotel booking platform that connects clients with hotel owners, enabling efficient reservation processes. The system provides tools for booking management, room availability checking, and a social rating system for user feedback.

## Key Features
- User authentication and role-based access control
- Hotel and room listings with detailed information
- Advanced search and filtering options
- Reservation management system
- Social rating and review system
- Hotel owner dashboard for property management
- Admin panel for system maintenance and user management
- Promotions and special offers management

## Technology Stack
- **Backend**: Spring Boot, Spring Security, Spring Data JPA
- **Database**: MySQL
- **ORM**: Hibernate
- **API**: RESTful API
- **Documentation**: Swagger/OpenAPI
- **Authentication**: JWT (JSON Web Tokens)

## Project Structure
The project follows a clean architecture with separation of concerns:
- **Controller layer**: Handles HTTP requests and responses
- **Service layer**: Contains business logic
- **Repository layer**: Manages data access
- **Model layer**: Defines the domain entities
- **DTO layer**: Transfers data between layers
- **Exception handling**: Centralized exception management
- **Security**: Authentication and authorization

## Directory Structure
```
src/
├── main/
    ├── java/
    │   └── com/
    │       └── easysta/
    │           ├── config/
    │           │   ├── SecurityConfig.java
    │           │   ├── JwtConfig.java
    │           │   ├── WebConfig.java
    │           │   └── SwaggerConfig.java
    │           ├── controller/
    │           │   ├── AuthController.java
    │           │   ├── UserController.java
    │           │   ├── ClientController.java
    │           │   ├── HotelOwnerController.java
    │           │   ├── AdminController.java
    │           │   ├── HotelController.java
    │           │   ├── RoomController.java
    │           │   ├── ReservationController.java
    │           │   ├── RatingController.java
    │           │   └── PromotionController.java
    │           ├── dto/
    │           │   ├── request/
    │           │   │   ├── UserDTO.java
    │           │   │   ├── LoginDTO.java
    │           │   │   ├── HotelDTO.java
    │           │   │   ├── RoomDTO.java
    │           │   │   ├── ReservationDTO.java
    │           │   │   ├── RatingDTO.java
    │           │   │   ├── RegisterDTO.java
    │           │   │   ├── AdminDTO.java
    │           │   │   ├── ClientDTO.java
    │           │   │   ├── HotelOwnerDTO.java
    │           │   │   └── PromotionDTO.java
    │           │   └── response/
    │           │       ├── UserResponseDTO.java
    │           │       ├── HotelResponseDTO.java
    │           │       ├── RoomResponseDTO.java
    │           │       ├── ReservationResponseDTO.java
    │           │       ├── RatingResponseDTO.java
    │           │       ├── PromotionResponseDTO.java
    │           │       ├── JwtResponseDTO.java
    │           │       └── ApiResponseDTO.java
    │           ├── exception/
    │           │   ├── GlobalExceptionHandler.java
    │           │   ├── ResourceNotFoundException.java
    │           │   ├── BadRequestException.java
    │           │   ├── UnauthorizedException.java
    │           │   └── ForbiddenException.java
    │           ├── model/
    │           │   ├── User.java
    │           │   ├── Client.java
    │           │   ├── HotelOwner.java
    │           │   ├── SystemAdmin.java
    │           │   ├── Hotel.java
    │           │   ├── Room.java
    │           │   ├── Reservation.java
    │           │   ├── Rating.java
    │           │   ├── Promotion.java
    │           │   ├── RoomStatus.java
    │           │   ├── PromotionStatus.java
    │           │   ├── HotelStatus.java
    │           │   └── enums/
    │           │       ├── UserRole.java
    │           │       ├── HotelStatus.java
    │           │       ├── RoomStatus.java
    │           │       ├── ReservationStatus.java
    │           │       ├── PaymentStatus.java
    │           │       ├── PromotionStatus.java
    │           │       └── RoomType.java
    │           ├── repository/
    │           │   ├── UserRepository.java
    │           │   ├── ClientRepository.java
    │           │   ├── HotelOwnerRepository.java
    │           │   ├── SystemAdminRepository.java
    │           │   ├── HotelRepository.java
    │           │   ├── RoomRepository.java
    │           │   ├── ReservationRepository.java
    │           │   ├── RatingRepository.java
    │           │   ├── HotelRepository.java
    │           │   └── PromotionRepository.java
    │           ├── security/
    │           │   ├── JwtTokenProvider.java
    │           │   ├── JwtAuthenticationFilter.java
    │           │   ├── JwtAuthorizationFilter.java
    │           │   └── UserDetailsServiceImpl.java
    │           ├── service/
    │           │   ├── UserService.java
    │           │   ├── ClientService.java
    │           │   ├── HotelOwnerService.java
    │           │   ├── SystemAdminService.java
    │           │   ├── HotelService.java
    │           │   ├── RoomService.java
    │           │   ├── ReservationService.java
    │           │   ├── RatingService.java
    │           │   ├── PromotionService.java
    │           │   ├── AuthService.java
    │           │   └── JwtService.java
    │           ├── util/
    │           │   ├── DateUtils.java
    │           │   ├── ValidationUtils.java
    │           │   └── PriceCalculator.java
    │           └── EasyStayApplication.java
    └── resources/
        ├── application.properties
        ├── application-dev.properties
        └── db/
            └── migration/

```

## Domain Entities
- **User**: Base class for all system users
- **Client**: End-users who book hotels
- **HotelOwner**: Manages hotels and rooms
- **SystemAdmin**: Administrative access to the entire system
- **Hotel**: Contains information about hotels
- **Room**: Details about hotel rooms
- **Reservation**: Manages booking information
- **Rating**: User reviews and ratings
- **Promotion**: Special offers and discounts

## API Endpoints

### Admin
- `GET /api/admin` - Get admin
- `POST /api/admin` - Create admin

### Auth
- `POST /api/auth` - Create auth

### Clients
- `GET /api/clients` - Get clients
- `POST /api/clients` - Create clients

### Hotels
- `GET /api/hotels` - Get hotels
- `POST /api/hotels` - Create hotels

### Hotel-owners
- `GET /api/hotel-owners` - Get hotel owners
- `POST /api/hotel-owners` - Create hotel owners

### Promotions
- `GET /api/promotions` - Get promotions
- `POST /api/promotions` - Create promotions

### Ratings
- `GET /api/ratings` - Get ratings
- `POST /api/ratings` - Create ratings

### Reservations
- `GET /api/reservations` - Get reservations
- `POST /api/reservations` - Create reservations

### Rooms
- `GET /api/rooms` - Get rooms
- `POST /api/rooms` - Create rooms

### Users
- `GET /api/users` - Get users
- `POST /api/users` - Create users

## Database Schema
The database design follows the entity relationships defined in the class diagram. Key relationships include:
- One-to-many between Hotel and Room
- One-to-many between Hotel and Rating
- One-to-many between Hotel and Promotion
- One-to-many between Room and Reservation
- One-to-many between Client and Reservation
- One-to-many between Client and Rating

## Security
- JWT-based authentication
- Role-based access control
- Password encryption
- Protection against common web vulnerabilities
- Request validation and sanitization

## Getting Started

### Prerequisites
- JDK 17 or higher
- Maven 3.6.x or higher
- MySQL 8.0.x

### Configuration
1. Clone the repository
2. Configure database settings in `application.properties`
3. Run database migrations using Flyway

### Running the Application
```bash
# Build the project
mvn clean install

# Run the application
mvn spring-boot:run
```

### API Documentation
Once the application is running, access the Swagger UI at:
```
http://localhost:8080/swagger-ui.html

# Run specific test class
mvn test -Dtest=HotelServiceTest
```

## Contribution Guidelines
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request
