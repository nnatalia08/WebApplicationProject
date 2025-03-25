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
- **Testing**: JUnit, Mockito

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
│   ├── java/
│   │   └── com/
│   │       └── easysta/
│   │           ├── config/
│   │           │   ├── SecurityConfig.java
│   │           │   ├── JwtConfig.java
│   │           │   ├── WebConfig.java
│   │           │   └── SwaggerConfig.java
│   │           ├── controller/
│   │           │   ├── AuthController.java
│   │           │   ├── UserController.java
│   │           │   ├── ClientController.java
│   │           │   ├── HotelOwnerController.java
│   │           │   ├── AdminController.java
│   │           │   ├── HotelController.java
│   │           │   ├── RoomController.java
│   │           │   ├── ReservationController.java
│   │           │   ├── RatingController.java
│   │           │   └── PromotionController.java
│   │           ├── dto/
│   │           │   ├── request/
│   │           │   │   ├── UserDTO.java
│   │           │   │   ├── LoginDTO.java
│   │           │   │   ├── HotelDTO.java
│   │           │   │   ├── RoomDTO.java
│   │           │   │   ├── ReservationDTO.java
│   │           │   │   ├── RatingDTO.java
│   │           │   │   └── PromotionDTO.java
│   │           │   └── response/
│   │           │       ├── UserResponseDTO.java
│   │           │       ├── HotelResponseDTO.java
│   │           │       ├── RoomResponseDTO.java
│   │           │       ├── ReservationResponseDTO.java
│   │           │       ├── RatingResponseDTO.java
│   │           │       ├── PromotionResponseDTO.java
│   │           │       ├── JwtResponseDTO.java
│   │           │       └── ApiResponseDTO.java
│   │           ├── exception/
│   │           │   ├── GlobalExceptionHandler.java
│   │           │   ├── ResourceNotFoundException.java
│   │           │   ├── BadRequestException.java
│   │           │   ├── UnauthorizedException.java
│   │           │   └── ForbiddenException.java
│   │           ├── model/
│   │           │   ├── User.java
│   │           │   ├── Client.java
│   │           │   ├── HotelOwner.java
│   │           │   ├── SystemAdmin.java
│   │           │   ├── Hotel.java
│   │           │   ├── Room.java
│   │           │   ├── Reservation.java
│   │           │   ├── Rating.java
│   │           │   ├── Promotion.java
│   │           │   └── enums/
│   │           │       ├── UserRole.java
│   │           │       ├── HotelStatus.java
│   │           │       ├── RoomStatus.java
│   │           │       ├── ReservationStatus.java
│   │           │       ├── PaymentStatus.java
│   │           │       ├── PromotionStatus.java
│   │           │       └── RoomType.java
│   │           ├── repository/
│   │           │   ├── UserRepository.java
│   │           │   ├── ClientRepository.java
│   │           │   ├── HotelOwnerRepository.java
│   │           │   ├── SystemAdminRepository.java
│   │           │   ├── HotelRepository.java
│   │           │   ├── RoomRepository.java
│   │           │   ├── ReservationRepository.java
│   │           │   ├── RatingRepository.java
│   │           │   └── PromotionRepository.java
│   │           ├── service/
│   │           │   ├── UserService.java
│   │           │   ├── ClientService.java
│   │           │   ├── HotelOwnerService.java
│   │           │   ├── SystemAdminService.java
│   │           │   ├── HotelService.java
│   │           │   ├── RoomService.java
│   │           │   ├── ReservationService.java
│   │           │   ├── RatingService.java
│   │           │   ├── PromotionService.java
│   │           │   ├── AuthService.java
│   │           │   ├── JwtService.java
│   │           │   └── impl/
│   │           │       ├── UserServiceImpl.java
│   │           │       ├── ClientServiceImpl.java
│   │           │       ├── HotelOwnerServiceImpl.java
│   │           │       ├── SystemAdminServiceImpl.java
│   │           │       ├── HotelServiceImpl.java
│   │           │       ├── RoomServiceImpl.java
│   │           │       ├── ReservationServiceImpl.java
│   │           │       ├── RatingServiceImpl.java
│   │           │       ├── PromotionServiceImpl.java
│   │           │       ├── AuthServiceImpl.java
│   │           │       └── JwtServiceImpl.java
│   │           ├── security/
│   │           │   ├── JwtTokenProvider.java
│   │           │   ├── JwtAuthenticationFilter.java
│   │           │   ├── JwtAuthorizationFilter.java
│   │           │   └── UserDetailsServiceImpl.java
│   │           ├── util/
│   │           │   ├── DateUtils.java
│   │           │   ├── ValidationUtils.java
│   │           │   └── PriceCalculator.java
│   │           └── EasyStayApplication.java
│   └── resources/
│       ├── application.properties
│       ├── application-dev.properties
│       ├── application-prod.properties
│       └── db/
│           └── migration/
│               ├── V1__create_tables.sql
│               └── V2__insert_initial_data.sql
└── test/
    └── java/
        └── com/
            └── easysta/
                ├── controller/
                ├── service/
                └── repository/
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

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Authenticate user and get token

### Users
- `GET /api/users/{id}` - Get user by ID
- `PUT /api/users/{id}` - Update user
- `DELETE /api/users/{id}` - Delete user (admin only)

### Hotels
- `GET /api/hotels` - Get all hotels
- `GET /api/hotels/{id}` - Get hotel by ID
- `POST /api/hotels` - Create new hotel (hotel owner only)
- `PUT /api/hotels/{id}` - Update hotel (hotel owner only)
- `DELETE /api/hotels/{id}` - Delete hotel (hotel owner only)
- `GET /api/hotels/search` - Search hotels by criteria

### Rooms
- `GET /api/hotels/{hotelId}/rooms` - Get all rooms for a hotel
- `GET /api/hotels/{hotelId}/rooms/{id}` - Get room by ID
- `POST /api/hotels/{hotelId}/rooms` - Add room to hotel (hotel owner only)
- `PUT /api/hotels/{hotelId}/rooms/{id}` - Update room (hotel owner only)
- `DELETE /api/hotels/{hotelId}/rooms/{id}` - Delete room (hotel owner only)
- `GET /api/hotels/{hotelId}/rooms/available` - Get available rooms for a date range

### Reservations
- `GET /api/reservations` - Get all reservations (client: own only, owner: hotel only)
- `GET /api/reservations/{id}` - Get reservation by ID
- `POST /api/reservations` - Create new reservation
- `PUT /api/reservations/{id}` - Update reservation status
- `DELETE /api/reservations/{id}` - Cancel reservation

### Ratings
- `GET /api/hotels/{hotelId}/ratings` - Get all ratings for a hotel
- `POST /api/hotels/{hotelId}/ratings` - Add rating to hotel
- `PUT /api/hotels/{hotelId}/ratings/{id}` - Update rating (own only)
- `DELETE /api/hotels/{hotelId}/ratings/{id}` - Delete rating (own or admin only)

### Promotions
- `GET /api/hotels/{hotelId}/promotions` - Get all promotions for a hotel
- `POST /api/hotels/{hotelId}/promotions` - Add promotion (hotel owner only)
- `PUT /api/hotels/{hotelId}/promotions/{id}` - Update promotion (hotel owner only)
- `DELETE /api/hotels/{hotelId}/promotions/{id}` - Delete promotion (hotel owner only)

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
```

## Testing
```bash
# Run all tests
mvn test

# Run specific test class
mvn test -Dtest=HotelServiceTest
```

## Contribution Guidelines
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request
