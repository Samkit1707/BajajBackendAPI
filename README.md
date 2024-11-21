# BajajBackendAPI

Project Overview
This backend project is a REST API built using Java and Spring Boot. It supports two endpoints, POST and GET, designed to process JSON input and return structured responses based on specific requirements. The backend handles user input validation, performs computations, and processes file uploads.

Endpoints
1. POST /bfhl
Description: Processes a JSON payload and returns structured data as per requirements.
Request:
Accepts a JSON object containing:
json
Copy code
{
  "data": ["A", "B", "1", "2"]
}
Supports optional Base64-encoded file uploads.
Response:
json
Copy code
{
  "is_success": true,
  "user_id": "john_doe_17091999",
  "email": "john.doe@college.edu",
  "roll_number": "123456",
  "numbers": [1, 2],
  "alphabets": ["A", "B"],
  "highestLowercaseAlphabet": "z",
  "is_prime_found": true,
  "file": {
    "file_valid": true,
    "file_mime_type": "application/pdf",
    "file_size_kb": 45
  }
}
Logic:
Extracts numbers and alphabets from the input array.
Determines the highest lowercase letter if present.
Checks for prime numbers in the input data.
Validates and processes an optional file.
2. GET /bfhl
Description: Returns a predefined operation_code.
Response:
json
Copy code
{
  "operation_code": "BFHL_001"
}
Installation & Setup
Prerequisites:
Java: Ensure Java 11+ is installed.
Maven: Install Maven for dependency management.
Spring Boot: Framework used to build the REST API.
Steps:
Clone the repository:
bash
Copy code
git clone https://github.com/your-repository-link.git
cd backend-rest-api
Build the project:
bash
Copy code
mvn clean install
Run the application:
bash
Copy code
mvn spring-boot:run
Access the API:
POST Endpoint: http://localhost:8080/bfhl
GET Endpoint: http://localhost:8080/bfhl
Testing the API
Use tools like Postman or curl to send requests.
Example POST Request:
bash
Copy code
curl -X POST -H "Content-Type: application/json" -d '{"data": ["A", "b", "3"]}' http://localhost:8080/bfhl
Example GET Request:
bash
Copy code
curl -X GET http://localhost:8080/bfhl
Hosting
The backend is hosted on Render

API URL: https://your-backend-url.com/bfhl
Directory Structure
bash
Copy code
backend-rest-api/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── com.example.bfhl/
│   │   │   │   ├── controller/   # API Controllers
│   │   │   │   ├── service/      # Business Logic
│   │   │   │   ├── model/        # Request/Response Models
│   │   │   │   ├── utils/        # Utility Methods
│   │   │   │   ├── Application.java  # Main Class
│   ├── test/                     # Unit Tests
├── pom.xml                       # Maven Dependencies
├── README.md                     # Documentation
Future Enhancements
Add user authentication and authorization.
Extend response filtering for additional data categories.
Deploy with CI/CD pipelines for automated updates.
