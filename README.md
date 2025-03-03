# Blogging Application

## Overview

This is a **Spring Boot-based Blogging Application** that allows users to create, manage, and interact with blog posts. The application supports authentication, role-based access, and essential blogging features like comments, pagination, searching, and sorting.

## Features

### **User Features**

- **Post Management**: Users can create, update, and delete their posts.
- **Category-Based Posts**: Users can assign categories to posts.
- **View Posts**: Users can view their own posts and all available posts.
- **Commenting System**:
  - Users can add comments to posts.
  - Users can update and delete their own comments.
  - Users can view all comments on a post.
- **Search & Sorting**:
  - Search for posts using keywords.
  - Sort posts based on different parameters.
  - Pagination for efficient data retrieval.

### **Admin Features**

- Manage all posts and comments.
- Assign roles and permissions.

### **Security Features**

- **JWT Authentication**: Secure APIs with JSON Web Token.
- **Role-Based Access Control (RBAC)**: Admin and normal users have different permissions.

## Tech Stack

- **Backend**: Java, Spring Boot, Spring Security, JWT, Hibernate, JPA
- **Database**: MySQL / PostgreSQL
- **Build Tool**: Maven / Gradle
- **API Documentation**: Swagger

## Installation & Setup

### **Prerequisites**

- Java 17+
- Maven or Gradle
- MySQL or PostgreSQL database
- Postman (for API testing)

### **Clone the Repository**

```sh
 git clone https://github.com/your-username/blogging-app.git
 cd blogging-app
```

### **Configure Database**

Update `application.properties` or `application.yml` with database details:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/blog_db
spring.datasource.username=root
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
```

### **Build & Run**

```sh
 mvn clean install
 mvn spring-boot:run
```

### **API Endpoints**

| Method | Endpoint                 | Description                 | Access      |
| ------ | ------------------------ | --------------------------- | ----------- |
| POST   | /api/auth/register       | Register a new user         | Public      |
| POST   | /api/auth/login          | Authenticate user & get JWT | Public      |
| POST   | /api/posts               | Create a new post           | User/Admin  |
| GET    | /api/posts               | Retrieve all posts          | Public      |
| GET    | /api/posts/{id}          | Retrieve a specific post    | Public      |
| PUT    | /api/posts/{id}          | Update post                 | Owner/Admin |
| DELETE | /api/posts/{id}          | Delete post                 | Owner/Admin |
| POST   | /api/posts/{id}/comments | Add a comment               | User/Admin  |
| GET    | /api/posts/{id}/comments | Get all comments on a post  | Public      |
| PUT    | /api/comments/{id}       | Update comment              | Owner       |
| DELETE | /api/comments/{id}       | Delete comment              | Owner/Admin |

### **Authentication & Authorization**

- JWT-based authentication
- Include JWT in headers:
  ```sh
  Authorization: Bearer your_jwt_token
  ```
- Role-based access control:
  - **Admin**: Full control over posts and comments
  - **User**: Manage their own posts and comments

### **Pagination & Sorting**

- Use query parameters to control pagination and sorting:
  ```sh
  GET /api/posts?page=1&size=10&sort=title,asc
  ```

## Contributing

1. Fork the repository
2. Create a new branch (`feature-branch`)
3. Commit your changes
4. Push to the branch
5. Submit a pull request

## License

This project is licensed under the **MIT License**. See the `LICENSE` file for details.

---

🚀 **Happy Blogging!**

