# sweet-cupcake-shop
object-Oriented Java application for bakery inventory management with role-based access control

# 🧁 Sweet Cupcake Shop Management System

[![Java](https://img.shields.io/badge/Java-8+-orange.svg)](https://www.oracle.com/java/)
[![Swing](https://img.shields.io/badge/GUI-Java%20Swing-blue.svg)](https://docs.oracle.com/javase/tutorial/uiswing/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A comprehensive Object-Oriented Java application for managing bakery inventory with role-based access control, demonstrating all six fundamental OOP concepts.

![Login Screen](Documentation/screenshots/login-screen.png)

## 📑 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [OOP Concepts Demonstrated](#oop-concepts-demonstrated)
- [Technologies Used](#technologies-used)
- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [UML Diagrams](#uml-diagrams)
- [Screenshots](#screenshots)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## 🎯 Overview

The Sweet Cupcake Shop Management System is a desktop application developed as part of the CSE4006 Object-Oriented Programming course at Cardiff Metropolitan University. The system provides an efficient solution for managing cupcake inventory, user accounts, and role-based operations in a bakery environment.

### Key Highlights

- ✅ **Complete OOP Implementation** - Demonstrates all 6 fundamental concepts
- ✅ **Role-Based Access Control** - Separate interfaces for Cashiers and Managers
- ✅ **File-Based Persistence** - Reliable data storage without database dependency
- ✅ **Professional GUI** - Clean, intuitive Java Swing interface
- ✅ **Well-Documented** - Comprehensive documentation and UML diagrams

## ✨ Features

### 🔐 Authentication System
- Secure login with username/password validation
- Role-based dashboard routing (Cashier/Manager)
- Session management with logout functionality

### 👤 Cashier Functions
- **View All Cupcakes** - Display complete inventory in table format
- **Add New Cupcake** - Create new products with validation
- **Search by Category** - Filter cupcakes by 6 predefined categories
- **Data Validation** - Price and stock quantity checks

### 👨‍💼 Manager Functions
- **All Cashier Capabilities** - Inherited through multi-level inheritance
- **Create Cashier Accounts** - Add new staff with username validation
- **View All Users** - Display system user directory
- **Advanced Access Control** - Manager-only features

### 📊 Cupcake Categories
1. Classic Flavors
2. Red Velvet
3. Fruity Delights
4. Seasonal Specials
5. Custom Orders
6. Gluten-Free

## 🎓 OOP Concepts Demonstrated

This project showcases all six fundamental Object-Oriented Programming concepts:

### 1. **Object**
- Creation of Cupcake, Cashier, and Manager instances
- Real-world entity representation

### 2. **Class**
- User, Cashier, Manager, Cupcake, Category classes
- Blueprint-based object creation

### 3. **Abstraction**
```java
public abstract class User {
    public abstract boolean login(String username, String password);
}
```

### 4. **Inheritance**
```
User (Abstract)
    ↑
    │ extends
    │
Cashier
    ↑
    │ extends
    │
Manager
```
- Multi-level inheritance hierarchy
- IS-A relationships

### 5. **Encapsulation**
- Private attributes with public getters/setters
- Data protection and controlled access
- Input validation in setters

### 6. **Polymorphism**
- Method overriding (login() in different user types)
- Constructor overloading in Cupcake class
- Runtime dynamic behavior

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| **Java 8+** | Core programming language |
| **Java Swing** | GUI framework |
| **NetBeans IDE** | Development environment |
| **File I/O** | Data persistence |
| **Draw.io** | UML diagram creation |

## 💻 System Requirements

### Minimum Requirements
- **Processor:** Intel Core i3 or equivalent
- **RAM:** 4GB
- **Storage:** 100MB free space
- **Display:** 1024x768 resolution
- **OS:** Windows 7+, macOS, Linux

### Software Requirements
- **JDK:** 8 or higher
- **IDE:** NetBeans (recommended), Eclipse, or IntelliJ IDEA

## 📥 Installation

### Option 1: Clone Repository
```bash
# Clone the repository
git clone https://github.com/yourusername/sweet-cupcake-shop.git

# Navigate to project directory
cd sweet-cupcake-shop
```

### Option 2: Download ZIP

1. Click the green "Code" button
2. Select "Download ZIP"
3. Extract to your desired location

### Running the Application

#### From NetBeans:
1. Open NetBeans IDE
2. File → Open Project
3. Select the `sweet-cupcake-shop` folder
4. Right-click project → Run

#### From Command Line:
```bash
# Navigate to src directory
cd src

# Compile
javac sweetcupcakeshop/SweetCupcakeShop.java

# Run
java sweetcupcakeshop.SweetCupcakeShop
```

## 🚀 Usage

### Default Login Credentials

**Manager Account:**
```
Username: admin
Password: admin123
```

**Cashier Account:**
```
Username: cashier
Password: cashier123
```

### Quick Start Guide

1. **Launch Application** - Run SweetCupcakeShop.java
2. **Login** - Use default credentials
3. **Explore Features:**
   - View inventory
   - Add new cupcakes
   - Search by category
   - (Manager only) Create accounts and view users

For detailed instructions, see the [User Manual](Documentation/User_Manual.pdf).

## 📁 Project Structure
```
sweet-cupcake-shop/
│
├── src/
│   ├── controllers/
│   │   └── SystemController.java      # Authentication & session management
│   │
│   ├── models/
│   │   ├── Category.java              # Cupcake categories enumeration
│   │   ├── User.java                  # Abstract base class
│   │   ├── Cashier.java               # Cashier user implementation
│   │   ├── Manager.java               # Manager user implementation
│   │   └── Cupcake.java               # Cupcake entity
│   │
│   ├── utils/
│   │   └── FileHandler.java           # File I/O operations
│   │
│   ├── views/
│   │   ├── LoginFrame.java            # Login interface
│   │   ├── CashierDashboard.java      # Cashier main view
│   │   ├── ManagerDashboard.java      # Manager main view
│   │   ├── AddCupcakeDialog.java      # Add cupcake form
│   │   └── SearchDialog.java          # Search functionality
│   │
│   └── sweetcupcakeshop/
│       └── SweetCupcakeShop.java      # Main entry point
│
├── data/
│   ├── cupcakes.txt                   # Cupcake inventory data
│   └── users.txt                      # User account data
│
├── Documentation/
│   ├── Main_Report.pdf                # Complete system documentation
│   ├── User_Manual.pdf                # User guide with screenshots
│   └── UML_Diagrams/
│       ├── UseCase_Diagram.png
│       ├── Class_Diagram.png
│       └── Sequence_Diagrams.png
│
├── .gitignore                         # Git ignore file
├── README.md                          # This file
└── LICENSE                            # MIT License
```

## 📐 UML Diagrams

### Use Case Diagram
![Use Case Diagram](Documentation/UML_Diagrams/UseCase_Diagram.png)

Shows actors (Cashier, Manager) and their interactions with the system.

### Class Diagram
![Class Diagram](Documentation/UML_Diagrams/Class_Diagram.png)

Illustrates class structure, relationships, and OOP concepts.

### Sequence Diagrams
- **Login Process** - User authentication flow
- **Add Cupcake** - Product creation process
- **Search Cupcake** - Category-based filtering
- **Create Cashier** - Manager account creation

*Full diagrams available in [Documentation/UML_Diagrams/](Documentation/UML_Diagrams/)*

## 📸 Screenshots

### Login Screen
![Login](Documentation/screenshots/login.png)

### Cashier Dashboard
![Cashier Dashboard](Documentation/screenshots/cashier-dashboard.png)

### Manager Dashboard
![Manager Dashboard](Documentation/screenshots/manager-dashboard.png)

### Add Cupcake Dialog
![Add Cupcake](Documentation/screenshots/add-cupcake.png)

## 📚 Documentation

Comprehensive documentation is available in the `Documentation/` folder:

- **[Main Report](Documentation/Main_Report.pdf)** - Complete system documentation
- **[User Manual](Documentation/User_Manual.pdf)** - Step-by-step user guide
- **[UML Diagrams](Documentation/UML_Diagrams/)** - All system diagrams

## 🏗️ Architecture

The system follows a **layered architecture** pattern:
```
┌─────────────────────────────────┐
│     Presentation Layer          │
│  (Views - Swing Components)     │
└─────────────────────────────────┘
              ↕
┌─────────────────────────────────┐
│     Business Logic Layer        │
│  (Controllers - System Logic)   │
└─────────────────────────────────┘
              ↕
┌─────────────────────────────────┐
│        Data Layer               │
│  (Models - Domain Objects)      │
└─────────────────────────────────┘
              ↕
┌─────────────────────────────────┐
│     Persistence Layer           │
│  (FileHandler - Data Storage)   │
└─────────────────────────────────┘
```

## 🧪 Testing

The system has been tested for:

- ✅ User authentication (valid/invalid credentials)
- ✅ Role-based access control
- ✅ CRUD operations on cupcakes
- ✅ Input validation (price, stock, empty fields)
- ✅ Category-based search
- ✅ File persistence
- ✅ Session management
- ✅ Error handling

## 🔮 Future Enhancements

Potential improvements for future versions:

- [ ] Database integration (MySQL/PostgreSQL)
- [ ] Sales tracking and reporting
- [ ] Inventory alerts for low stock
- [ ] Password encryption
- [ ] Export to Excel/PDF
- [ ] Advanced search filters
- [ ] Customer management
- [ ] Order processing system
- [ ] RESTful API
- [ ] Web interface

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**[Your Name]**
- Student ID: [Your ID]
- Institution: Cardiff Metropolitan University (ICBT Campus)
- Module: CSE4006 - Object Oriented Programming
- Batch: HDSE 25.2

## 🙏 Acknowledgments

- Module Leader: upeka@icbtcampus.edu.lk
- Cardiff Metropolitan University
- ICBT Campus - Kandy Innovation Centre

## 📧 Contact

For questions or feedback:

- **GitHub Issues:** [Create an issue](https://github.com/yourusername/sweet-cupcake-shop/issues)
- **Email:** your.email@example.com

---

**⭐ If you found this project helpful, please give it a star!**

---

*Developed with ❤️ as part of CSE4006 Object Oriented Programming coursework*
