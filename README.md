# Go API

Go API is a service for managing customer, product, employee, and transaction data for laundry purposes. This documentation provides details on how to use the API, including endpoints for adding, updating, and deleting customer, product, employee, and transaction data.

## Table of Contents

1. [Installation](#1-installation)
   - [Clone Repository](#11-clone-repository)
   - [Install Dependencies](#12-install-dependencies)
2. [Database Configuration](#2-database-configuration)
3. [Database Migration](#3-database-migration)
4. [API Usage](#4-api-usage)
   - [Customers](#41-customers)
   - [Products](#42-products)
   - [Employees](#43-employees)
   - [Transactions](#44-transactions)

## 1. Installation

### 1.1 Clone Repository

```bash
git clone https://github.com/arjunstrw/go-api.git
cd go-api
```

### 1.2 Intall Dependencies

```bash
go mod tidy
```

## 2. Database Configuration

Open the `main.go` file and adjust the database connection settings such as host, port, username, password, and database name.

```go
const (
	DBHost     = "localhost"
	DBPort     = 5432
	DBUser     = "postgres"
	DBPassword = "yourpassword"
	DBName     = "enigma_laundry"
)
```

## 3. Database Migration

Make sure to the run the database migration to create the required tables.

```bash
go run migrate.go
```

## 4. API Usage

### 4.1 Customers

#### 4.1.1 Add New Customer

- **Endpoint : `POST /customers`**
- **Sample Request Body:**

```json
{
  "name": "John Doe",
  "phonenumber": "1234567890",
  "address": "123 Minor St"
}
```

#### 4.1.2 Get Customer Information

- **Endpoint : `GET /customers/{id}`**

#### 4.1.3 Update Customer Data

- **Endpoint : `PUT /customers/{id}`**
- **Sample Request Body:**

```json
{
  "name": "Updated Name",
  "phonenumber": "0987654321",
  "address": "Updated Address"
}
```

#### 4.1.4 Delete Customer

- **Endpoint: `DELETE /customers/{id}`**

### 4.2 Products

#### 4.1.1 Add New Products

- **Endpoint: `POST /products`**
- **Sample Request Body:**

```json
{
  "name": "Laundry Reguler",
  "quantity": 1,
  "unit": "KG",
  "price": 15000
}
```

#### 4.1.2 Get Product Information

- **Endpoint : `GET /products/{id}`**

#### 4.1.3 Update Product Data

- **Endpoint : `PUT /products/{id}`**
- **Sample Body Request**

```json
{
  "name": "New Product",
  "quantity": 2,
  "unit": "New Unit",
  "price": 28000
}
```

#### 4.1.4 Delete Product

- **Endpoint : `DELETE /products/{id}`**
