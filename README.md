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

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
https://github.com/latakant/Kodewala-Ecom-Project.git
cd Kodewala-Ecom-Project

