# 🛒 Terminal-Based E-Commerce System

A simple **terminal-based E-Commerce system** built with **Core Java** and **MySQL**. This project allows users to register, view products, place orders, and manage stock — all via the command line interface.

---

## 📦 Tech Stack

| Technology     | Description                        |
|----------------|------------------------------------|
| **Java**       | Core Java (OOP, JDBC)              |
| **MySQL**      | Relational Database                |
| **JDBC**       | Java Database Connectivity         |
| **Maven** *(optional)* | Project build & dependency management |
| **Git**        | Version control                    |

---

## ✨ Features

- ✅ User Registration & Login  
- 🛍️ Product Browsing  
- 🧾 Place & View Orders  
- 📦 Inventory / Stock Management  
- 🔐 Terminal-based access  

---

## 🗃️ Database Schema & Relationships

### Tables

1. **Users**
2. **Products**
3. **Orders**
4. **Order_Items**
5. **Inventory** *(optional if stock is separate)*

### Relationships

| Relationship        | Type         | Description                                |
|---------------------|--------------|--------------------------------------------|
| Users → Orders      | One-to-Many  | One user can place multiple orders         |
| Orders ↔ Products   | Many-to-Many | One order can contain multiple products    |
| Products → Inventory| One-to-One   | One product has a single stock record      |

## 🛠️ Database Schema (`schema.sql`)

```sql
 -- 🧑‍💼 Users Table
        CREATE TABLE users (
            id INT AUTO_INCREMENT PRIMARY KEY,
            username VARCHAR(50) UNIQUE NOT NULL,
            email VARCHAR(100) UNIQUE NOT NULL,
            password VARCHAR(100) NOT NULL,
            created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
        );
        
-- 📦 Products Table
        CREATE TABLE products (
            id INT AUTO_INCREMENT PRIMARY KEY,
            name VARCHAR(100) NOT NULL,
            description TEXT,
            price DECIMAL(10, 2) NOT NULL,
            created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
        );
        
-- 🧮 Inventory Table (One-to-One with Products)
        CREATE TABLE inventory (
            product_id INT PRIMARY KEY,
            stock INT NOT NULL DEFAULT 0,
            FOREIGN KEY (product_id) REFERENCES products(id) ON DELETE CASCADE
        );
        
-- 🧾 Orders Table (Many-to-One with Users)
        CREATE TABLE orders (
            id INT AUTO_INCREMENT PRIMARY KEY,
            user_id INT NOT NULL,
            total_price DECIMAL(10, 2) NOT NULL,
            status VARCHAR(20) DEFAULT 'Pending',
            order_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
            FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
        );
        
        -- 📑 Order Items Table (Many-to-Many between Orders and Products)
        CREATE TABLE order_items (
            id INT AUTO_INCREMENT PRIMARY KEY,
            order_id INT NOT NULL,
            product_id INT NOT NULL,
            quantity INT NOT NULL,
            price DECIMAL(10, 2) NOT NULL,
            FOREIGN KEY (order_id) REFERENCES orders(id) ON DELETE CASCADE,
            FOREIGN KEY (product_id) REFERENCES products(id) ON DELETE CASCADE
        );

---


## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
https://github.com/latakant/Kodewala-Ecom-Project.git
cd Kodewala-Ecom-Project
