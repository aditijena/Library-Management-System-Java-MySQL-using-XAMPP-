# 📚 Library Management System (Java + MySQL using XAMPP)

This project is a **Library Management System** developed using **MySQL (DBMS)** as the backend and connected to both **Java (JDBC)** and **PHP (XAMPP)** interfaces.  
It demonstrates how a centralized database can be accessed and managed using multiple front-end technologies — showcasing the integration of **Java with DBMS concepts**.

---

## 🚀 Features

- 📖 Add, Edit, and Delete Books  
- 🧍 Manage Students and Admins  
- 📅 Issue and Return Books  
- 🔍 Search and View Records  
- 🔗 Database Connectivity via JDBC (Java)  
- 🌐 Web Interface built using PHP and HTML (for demonstration)

---

## 🗄️ Database Details

- **Database Name:** `library_ms`  
- **Tables:** `admin`, `book`, `student`, `issuebook`, `returnbook`  
- **SQL File:** `library_managment.sql` *(import using phpMyAdmin in XAMPP)*  

The database is hosted locally through **XAMPP MySQL**, and the same data can be accessed by both the **Java application (via JDBC)** and the **PHP frontend**.

---

## ⚙️ Tech Stack

| Layer | Technology |
|--------|-------------|
| **Frontend (Web)** | PHP, HTML, CSS |
| **Frontend (Desktop)** | Java Swing |
| **Backend / Logic** | Java (JDBC) |
| **Database** | MySQL (via XAMPP) |
| **IDE Used** | NetBeans / Eclipse |
| **Connector** | MySQL Connector JAR |

---

## 🧠 Java + DBMS Integration

The Java application uses a dedicated class `DBConnection.java` to establish connectivity with MySQL:

```java
package jframe;
import java.sql.Connection;
import java.sql.DriverManager;

public class DBConnection {
    static Connection con = null;
    
    public static Connection getConnection() {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            con = DriverManager.getConnection("jdbc:mysql://localhost:3306/library_ms", "root", "");
        } catch(Exception e) {
            e.printStackTrace();
        }
        return con;
    }
}

