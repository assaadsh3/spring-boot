
# Library Management System (LMS) API

This Library Management System API allows librarians to manage books, patrons, and borrowing records. It is built with Spring Boot and uses RESTful APIs to handle operations such as adding, retrieving, updating, and deleting records.

## Project Structure

- **src/main/java/com/lms/lms**: Contains the main application files.
  - **controllers**: RESTful controllers for handling API requests.
  - **entities**: Data model classes for `Book`, `Patron`, and `BorrowingRecord`.
  - **repositories**: Interfaces for database access using Spring Data JPA.
  - **services**: Service layer containing business logic.
  - **exceptions**: Contains a global exception handler.
  - **aspects**: Logging aspect for monitoring performance and method calls.

## Requirements

- **Java 17 or higher**
- **Maven** for dependency management
- **Spring Boot** 3.3.5
- **H2** (in-memory database for testing) or another relational database

## Getting Started

### Clone the Repository

```bash
git clone <repository-url>
cd Final_Updated_Project/Project/lms
```

### Build the Project

Use Maven to build the project and download dependencies.

```bash
./mvnw clean install
```

### Run the Application

Start the application with the following command:

```bash
./mvnw spring-boot:run
```

The server will start on `http://localhost:8080`.

## API Endpoints

### Book Management

- **GET /api/books**: Retrieve a list of all books.
- **GET /api/books/{id}**: Retrieve details of a specific book by ID.
- **POST /api/books**: Add a new book.
- **PUT /api/books/{id}**: Update an existing book's information.
- **DELETE /api/books/{id}**: Delete a book by ID.

### Patron Management

- **GET /api/patrons**: Retrieve a list of all patrons.
- **GET /api/patrons/{id}**: Retrieve details of a specific patron by ID.
- **POST /api/patrons**: Add a new patron.
- **PUT /api/patrons/{id}**: Update an existing patron's information.
- **DELETE /api/patrons/{id}**: Delete a patron by ID.

### Borrowing Records

- **POST /api/borrow/{bookId}/patron/{patronId}**: Record a book borrowing by a patron.
- **PUT /api/return/{bookId}/patron/{patronId}**: Record the return of a borrowed book.

## Validation and Error Handling

The application includes input validation for all API requests, ensuring required fields and data formats. Errors are handled with a custom `GlobalExceptionHandler` that returns meaningful HTTP status codes and error messages.

## Additional Features

- **Logging with Aspects**: Uses AOP (Aspect-Oriented Programming) to log method calls, exceptions, and performance metrics.
- **Caching (Optional)**: Spring’s caching mechanisms can be configured to cache frequently accessed data, such as book details.
- **Transaction Management**: Utilizes `@Transactional` for managing transactions and ensuring data integrity.

## Running Tests

Unit tests are written for controllers and services using JUnit and Mockito. To run tests, use:

```bash
./mvnw test
```

## Configuration

- **application.properties**: Contains configurations for the Spring Boot application.
- Database configuration, logging, and other settings can be adjusted here.

## Troubleshooting

If you encounter issues:
- Ensure you have Java 23 and Maven installed.
- Check dependency versions in `pom.xml`.
- Verify database settings if using a non-H2 database.

## License

This project is licensed under the MIT License.
