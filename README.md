> Kodewala-Ecom-Project
# E-Commerce System (Terminal-Based)

A simple terminal-based e-commerce system built using Java and MySQL. This project allows users to register, place orders, and manage products.
Tech Stack

    Programming Language: Java (Core Java, JDBC)

    Database: MySQL

    ORM/Database Connectivity: JDBC (Java Database Connectivity)

    Build Tool: Maven (if applicable)

    Version Control: Git

# Features

    User Management: Register, login, and view user details.

    Product Management: View available products.

    Order Management: Place, track, and manage orders.

    Stock Management: Check product availability before placing an order.

# Database Schema
  ***Tables & Relationships***

    Users → One user can place multiple orders (One-to-Many)

    Orders → Each order can contain multiple products (Many-to-Many)

    Products → Each product has a stock count (One-to-One)
