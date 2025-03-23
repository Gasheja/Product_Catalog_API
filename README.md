# Product Catalog API

## Overview
The **Product Catalog API** is a simple RESTful API built using **Node.js, Express, and PostgreSQL**. It provides endpoints for managing products, including adding, retrieving, updating, and deleting product records. Additionally, the API is documented using **Swagger UI**.

## Features
- **CRUD operations** for managing products
- **PostgreSQL** as the database
- **Swagger API documentation** for easy reference
- **Express.js** for handling server requests
- **Secure and structured database queries** using parameterized queries

---

## Technologies Used
- **Node.js** - JavaScript runtime
- **Express.js** - Web framework for Node.js
- **PostgreSQL** - Relational database
- **Swagger UI** - API documentation tool

---

## Installation & Setup
### Prerequisites
Ensure you have the following installed:
- **Node.js** (Latest stable version)
- **PostgreSQL**
- **Git** (Optional)

### Steps to Setup
1. **Clone the Repository**
   ```sh
   git clone https://github.com/your-username/product-catalog-api.git
   cd product-catalog-api
   ```
2. **Install Dependencies**
   ```sh
   npm install
   ```
3. **Configure Database**
   - Create a PostgreSQL database named `product_catalog_api`.
   - Update your database credentials inside the `main.js` file:
     ```js
     const con = new Client({
       host: "localhost",
       user: "postgres",
       port: "5432",
       password: "YourPassword",
       database: "product_catalog_api",
     });
     ```
   - Run database migration (Ensure your `products` table exists):
     ```sql
     CREATE TABLE products (
       id SERIAL PRIMARY KEY,
       name VARCHAR(255) NOT NULL
     );
     ```
4. **Run the Server**
   ```sh
   node main.js
   ```
5. **Access Swagger API Documentation**
   Open your browser and visit:
   ```sh
   http://localhost:3000/api-docs
   ```

---

## API Endpoints
### Base URL: `http://localhost:3000`
| Method | Endpoint               | Description                 |
|--------|------------------------|-----------------------------|
| POST   | `/postData`            | Add a new product          |
| GET    | `/fetchData`           | Retrieve all products      |
| GET    | `/fetchbyId/:id`       | Get a product by ID        |
| PUT    | `/update/:id`          | Update a product by ID     |
| DELETE | `/deleteproduct/:id`   | Delete a product by ID     |

### Example Requests
#### 1. Create a New Product
**Request:**
```sh
POST /postData
```
**Body:**
```json
{
  "name": "Laptop",
  "id": 1
}
```

#### 2. Get All Products
**Request:**
```sh
GET /fetchData
```

#### 3. Get Product by ID
**Request:**
```sh
GET /fetchbyId/1
```

#### 4. Update a Product
**Request:**
```sh
PUT /update/1
```
**Body:**
```json
{
  "name": "Gaming Laptop"
}
```

#### 5. Delete a Product
**Request:**
```sh
DELETE /deleteproduct/1
```

---

## API Documentation (Swagger)
To access the API documentation, start the server and visit:
```sh
http://localhost:3000/api-docs
```
This provides an interactive UI to test the endpoints.

---



## Author
**Mugisha Gasheja**

