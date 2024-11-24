# NimapTest
## Spring Boot Category-Product Management API
This project is a RESTful API built with Spring Boot, implementing CRUD operations for categories and products. It uses JPA and Hibernate for database interaction, MySQL for persistence, and supports server-side pagination. Additionally, it establishes a one-to-many relationship between categories and products.

## Features
• CRUD operations for Categories and Products. <br>
• One-to-many relationship between Categories and Products.<br>
• Server-side pagination for listing categories and products.<br>
• MySQL as the database.<br>
• Annotation-based configuration (no XML).<br>
• Integrated with JPA and Hibernate for ORM.<br>

## Technologies Used
•  Java: Programming language.<br>
•  Spring Boot: Framework for building RESTful APIs.<br>
•  Spring Data JPA: For ORM and database operations.<br>
•  Hibernate: For database interaction.<br>
•  MySQL: Relational database for data storage.<br>
•  Lombok: Reduces boilerplate code.<br>
•  Maven: For dependency management and build.<br>

## Setup Instruction

### 1. Prerequisites
•  Java 17+<br>
•  Maven 3+<br>
•  MySQL Server<br>
•  IDE (e.g., IntelliJ IDEA, VS Code, Eclipse)<br>
•  Lombok Plugin (installed in your IDE)<br>

### 2. Clone the Repository
git clone https://github.com/your-username/NimapTest.git<br>
cd NimapTest

### 3. Configure Database
•  Create a MySQL database named NimapData.<br>
•  Update the database configuration in src/main/resources/application.properties:<br>
```
        spring.datasource.url=jdbc:mysql://localhost:3306/NimapData<br>
        spring.datasource.username=your_database_username<br>
        spring.datasource.password=your_database_password<br>
        spring.jpa.hibernate.ddl-auto=update<br>
        spring.jpa.show-sql=true<br>
        spring.jpa.properties.hibernate.format_sql=true<br>
```

### 4.Build The Project
Run the following commands to build the project and resolve dependencies:<br>
```
  ./mvnw clean install<br>
```
### 5. Run the Application
Start the application with:<br>
```
  ./mvnw spring-boot:run<br>
```
## API Endpoints
### Category Endpoint
| HTTP Method | Endpoint                              | Description                    |
|-------------|---------------------------------------|--------------------------------|
| GET         | `/api/categories?page={page}&size={size}` | Get all categories (paginated)|
| POST        | `/api/categories`                    | Create a new category          |
| GET         | `/api/categories/{id}`               | Get category by ID             |
| PUT         | `/api/categories/{id}`               | Update category by ID          |
| DELETE      | `/api/categories/{id}`               | Delete category by ID          |

### Product Endpoint
| HTTP Method | Endpoint                              | Description                    |
|-------------|---------------------------------------|--------------------------------|
| GET         | `/api/products?page={page}&size={size}` | Get all products (paginated)  |
| POST        | `/api/products`                      | Create a new product           |
| GET         | `/api/products/{id}`                 | Get product by ID (with category details) |
| PUT         | `/api/products/{id}`                 | Update product by ID           |
| DELETE      | `/api/products/{id}`                 | Delete product by ID           |

## Database Schema
### Category Table
| Column      | Type       | Constraints      |
|-------------|------------|------------------|
| id          | Long       | Primary Key      |
| name        | String     | Not Null         |
| description | String     | -                |

### Product table
| Column       | Type       | Constraints            |
|--------------|------------|------------------------|
| id           | Long       | Primary Key            |
| name         | String     | Not Null               |
| description  | String     | -                      |
| price        | Double     | -                      |
| category_id  | Long       | Foreign Key (Category) |

## Project Structure
```
src/main/java/com/mayuricode/demo
├── controller
│   ├── CategoryController.java
│   └── ProductController.java
├── entity
│   ├── Category.java
│   └── Product.java
├── repository
│   ├── CategoryRepository.java
│   └── ProductRepository.java
├── service
│   ├── CategoryService.java
│   └── ProductService.java
└── DemoApplication.java
```
<br>

## Testing
Use tools like Postman or cURL to test the API endpoints.<br>

Example POST request to create a category:
```
POST /api/categories
{
    "name": "Electronics",
    "description": "Devices and gadgets"
}
```
<br>
Feel free to replace placeholders like your-username, your-repository-name, your_database_name, and other specific values with your actual project details. Let me know if you need help customizing it further!

## Contact
Linkedin: https://www.linkedin.com/in/mayuri-mohite-353542248<br>
Email: mayurimohite1421@gmail.com


