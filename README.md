
# Product API's

The Product API is a RESTful web service built using Spring Boot. It provides CRUD operations for managing products and includes features such as input validation, error handling, and authentication. The API also includes detailed Swagger documentation for easy testing and integration.


## Features

- Create, Read, Update, and Delete (CRUD) operations for Product entities.

- Input validation using Bean Validation (e.g., @Valid and custom constraints).

- Global exception handling for consistent error responses.

- HTTP Basic Authentication for secure access.

- Swagger UI for API documentation and testing.

- Relational database integration with MySQL.



## Technologies Used

- Java 17
- Spring Boot 3.1+
- Spring Security
- Spring Data JPA
- Hibernate
- MySQL
- Swagger (Springdoc OpenAPI)

## Getting Started

**Prerequisites**

- Install Java 17+.
- Install Maven 3.8+.
- Install and set up MySQL.
## Setup and Run Instructions

Clone the project

```bash
  git clone https://link-to-project
```

Configure Database
  1. Open src/main/resources/application.properties.
  2. Update the database credentials:

```bash

spring.datasource.url=jdbc:mysql://localhost:3306/product_db
spring.datasource.username=your_db_username
spring.datasource.password=your_db_password

```
3. Ensure the database product_db exists. If not, create it:
```bash

CREATE DATABASE product_db;


```




## API Reference

### Swagger UI:

1.  Visit http://localhost:8080/swagger-ui.html for interactive API documentation.



### API Endpoints:


| HTTP Method	 | Endpoint     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `GET`      | `/products` | Retrieve all products
| `GET`      | `/products/{id}` | RRetrieve a product by ID
| `POST`      | `/products` | Create a new product
| `PUT`      | `/products/{id}` | 	Update an existing product
| `DELETE`      | `/products/{id}` | Delete a product by ID
 
 
 
 



## Authentication

- The API is secured with **HTTP Basic Authentication.**

- Default credentials:
  - **Username**: ``` admin ```
  - **Password**: ``` password ```

- Use these credentials to access all secured endpoints except Swagger.

- You can change the  credentials by updating the below properties in application.properties file:
```
security.user.name=your_username
security.user.password=your_password
```



## Example Request/Response

### Create Product

**Request**

**POST** /products

Request Body:

```bash
{
    "name": "Sample Product",
    "description": "This is a sample product.",
    "price": 99.99
}
```
**Response**

**Status Code**: 201 Created

Response Body:

```bash
{
    "id": 1,
    "name": "Sample Product",
    "description": "This is a sample product.",
    "price": 99.99
}
```
## Error Handling

The API provides consistent error responses. Example:

- **Validation Error:**

```bash
{
    "name": "Name is mandatory",
    "price": "Price must be greater than zero"
}
```

- **Resource Not Found:**

```bash
{
    "message": "Product not found with id: 10"
}
```
## Developed By

- Name: Kushal Bhayal
- Email: kushalbhayal.it@gmail.com
- GitHub: https://github.com/bhayalkushal/productapi-s.git

