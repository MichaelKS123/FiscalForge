# FiscalForge v1.0
**Advanced Expense Tracker with Analytics**  
**by Michael Semera**

---

## 📊 Overview

FiscalForge is a comprehensive personal finance management application built with Java and JavaFX. It provides powerful tools for tracking income and expenses, managing budgets, visualizing financial trends, and generating detailed reports. With a modern, user-friendly interface and robust database backend, FiscalForge makes personal finance management simple and insightful.

## ✨ Features

### Core Functionality

- **💰 Income & Expense Tracking**
  - Add, edit, and delete transactions
  - Categorize transactions (Food, Transport, Bills, etc.)
  - Date-based transaction management
  - Detailed transaction descriptions

- **📈 Advanced Analytics**
  - Interactive pie charts for expense categories
  - Line charts showing monthly trends
  - Real-time financial summaries
  - Budget vs. actual spending comparison

- **🎯 Budget Management**
  - Set category-based budgets
  - Monthly and yearly budget goals
  - Budget progress tracking
  - Overspending alerts

- **📊 Data Visualization**
  - Beautiful charts using JavaFX Charts
  - Color-coded financial indicators
  - Visual trend analysis
  - Dashboard with key metrics

- **📤 Export Capabilities**
  - Export to CSV format
  - Export to Excel (XLSX)
  - Customizable date ranges
  - All transaction data included

- **🔐 Secure Authentication**
  - Password-protected user accounts
  - SHA-256 password hashing
  - Individual user data isolation
  - Secure MySQL database

- **💾 Database Integration**
  - MySQL database backend
  - Automatic table creation
  - Data persistence
  - Efficient querying and indexing

---

## 🛠️ Technology Stack

| Component | Technology | Purpose |
|-----------|------------|---------|
| **Language** | Java 11+ | Core application logic |
| **GUI Framework** | JavaFX 17+ | User interface |
| **Database** | MySQL 8.0+ | Data persistence |
| **Charts** | JavaFX Charts | Data visualization |
| **Excel Export** | Apache POI | XLSX file generation |
| **Build Tool** | Maven/Gradle | Dependency management |

---

## 📦 Installation

### Prerequisites

1. **Java Development Kit (JDK) 11 or higher**
   ```bash
   java -version
   # Should show version 11 or higher
   ```

2. **JavaFX SDK 17+**
   - Download from: https://gluonhq.com/products/javafx/
   - Or use Maven dependencies (recommended)

3. **MySQL Server 8.0+**
   ```bash
   mysql --version
   # Ensure MySQL is running
   ```

4. **Maven** (recommended) or Gradle
   ```bash
   mvn --version
   ```

### Step 1: Clone or Download

```bash
# Create project directory
mkdir FiscalForge
cd FiscalForge
```

### Step 2: Create Project Structure

```
FiscalForge/
├── src/
│   └── main/
│       └── java/
│           └── com/
│               └── fiscalforge/
│                   └── FiscalForgeApp.java
├── pom.xml
└── README.md
```

### Step 3: Create `pom.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    
    <groupId>com.fiscalforge</groupId>
    <artifactId>fiscalforge</artifactId>
    <version>1.0</version>
    <packaging>jar</packaging>
    
    <name>FiscalForge</name>
    <description>Advanced Expense Tracker with Analytics</description>
    
    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.source>11</maven.compiler.source>
        <maven.compiler.target>11</maven.compiler.target>
        <javafx.version>17.0.2</javafx.version>
    </properties>
    
    <dependencies>
        <!-- JavaFX -->
        <dependency>
            <groupId>org.openjfx</groupId>
            <artifactId>javafx-controls</artifactId>
            <version>${javafx.version}</version>
        </dependency>
        <dependency>
            <groupId>org.openjfx</groupId>
            <artifactId>javafx-fxml</artifactId>
            <version>${javafx.version}</version>
        </dependency>
        
        <!-- MySQL Connector -->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>8.0.33</version>
        </dependency>
        
        <!-- JFreeChart (optional but recommended) -->
        <dependency>
            <groupId>org.jfree</groupId>
            <artifactId>jfreechart</artifactId>
            <version>1.5.3</version>
        </dependency>
        
        <!-- Apache POI for Excel Export -->
        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi-ooxml</artifactId>
            <version>5.2.3</version>
        </dependency>
    </dependencies>
    
    <build>
        <plugins>
            <plugin>
                <groupId>org.openjfx</groupId>
                <artifactId>javafx-maven-plugin</artifactId>
                <version>0.0.8</version>
                <configuration>
                    <mainClass>com.fiscalforge.FiscalForgeApp</mainClass>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
```

### Step 4: Setup MySQL Database

```bash
# Login to MySQL
mysql -u root -p

# Create database user (optional but recommended)
CREATE USER 'fiscalforge'@'localhost' IDENTIFIED BY 'your_secure_password';
GRANT ALL PRIVILEGES ON fiscalforge.* TO 'fiscalforge'@'localhost';
FLUSH PRIVILEGES;
```

**Update database credentials in code:**
```java
private static final String DB_URL = "jdbc:mysql://localhost:3306/fiscalforge";
private static final String DB_USER = "fiscalforge"; // or "root"
private static final String DB_PASSWORD = "your_password";
```

### Step 5: Build and Run

```bash
# Using Maven
mvn clean install
mvn javafx:run

# Or compile manually
javac --module-path /path/to/javafx-sdk/lib \
      --add-modules javafx.controls \
      -d bin src/main/java/com/fiscalforge/*.java

# Run
java --module-path /path/to/javafx-sdk/lib \
     --add-modules javafx.controls \
     -cp bin com.fiscalforge.FiscalForgeApp
```

---

## 🚀 Quick Start Guide

### First Launch

1. **Start the Application**
   ```bash
   mvn javafx:run
   ```

2. **Create Your Account**
   - Click "Create Account"
   - Enter username and password
   - (Optional) Enter email
   - Click OK

3. **Login**
   - Enter your credentials
   - Click "Login"

### Adding Your First Transaction

1. **Navigate to Transactions**
   - Click "Transactions" in the navigation bar

2. **Add Transaction**
   - Click "+ Add Transaction"
   - Select type (Income/Expense)
   - Enter amount
   - Choose category
   - Add description
   - Select date
   - Click OK

3. **View Dashboard**
   - Click "Dashboard" to see your financial overview

---

## 📖 User Guide

### Dashboard

The dashboard provides a quick overview of your finances:

- **Summary Cards**
  - Total Income (green)
  - Total Expenses (red)
  - Current Balance (blue/red)

- **Expense Breakdown Chart**
  - Pie chart showing expenses by category
  - Interactive - hover for details

- **Monthly Trend Chart**
  - Line chart showing expense trends
  - Last 12 months of data

- **Recent Transactions**
  - Table of last 10 transactions
  - Quick view of latest activity

### Transaction Management

**Add Transaction:**
1. Click "+ Add Transaction"
2. Fill in details
3. Save

**View Transactions:**
- All transactions displayed in table
- Sortable by column
- Filterable by date/category

**Export Data:**
- CSV: Click "Export to CSV"
- Excel: Click "Export to Excel"
- Choose save location

### Budget Management

**Set Budget Goals:**
1. Navigate to "Budget"
2. Select category
3. Set monthly/yearly amount
4. Monitor progress

**Track Spending:**
- Visual progress bars
- Percentage of budget used
- Alerts when approaching limit

### Reports & Analytics

**View Reports:**
1. Click "Reports" in navigation
2. Select report type:
   - Monthly Summary
   - Category Breakdown
   - Yearly Overview
   - Custom Date Range

**Export Reports:**
- PDF export (coming soon)
- Excel spreadsheets
- CSV data files

---

## 🎨 User Interface

### Color Scheme

| Element | Color | Usage |
|---------|-------|-------|
| Primary | #667eea (Purple) | Navigation, buttons |
| Success | #27ae60 (Green) | Income, positive |
| Danger | #e74c3c (Red) | Expenses, alerts |
| Info | #3498db (Blue) | Balance, info |
| Background | #f5f5f5 (Light Gray) | Main background |

### Responsive Design

- Adapts to window resizing
- Scrollable content areas
- Flexible layouts
- Readable fonts and spacing

---

## 🗄️ Database Schema

### Users Table

```sql
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) UNIQUE NOT NULL,
    password_hash VARCHAR(64) NOT NULL,
    email VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Transactions Table

```sql
CREATE TABLE transactions (
    id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT NOT NULL,
    date DATE NOT NULL,
    type VARCHAR(20) NOT NULL,      -- 'Income' or 'Expense'
    category VARCHAR(50) NOT NULL,
    description TEXT,
    amount DECIMAL(10, 2) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);
```

### Budgets Table

```sql
CREATE TABLE budgets (
    id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT NOT NULL,
    category VARCHAR(50) NOT NULL,
    amount DECIMAL(10, 2) NOT NULL,
    period VARCHAR(20) NOT NULL,    -- 'Monthly' or 'Yearly'
    start_date DATE NOT NULL,
    end_date DATE NOT NULL,
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);
```

---

## 🔐 Security Features

### Password Security

- **SHA-256 Hashing**: Passwords never stored in plain text
- **Salt Recommended**: Add salt for production use
- **Secure Storage**: Hashed passwords in database

### Data Protection

- **User Isolation**: Users can only see their own data
- **SQL Injection Prevention**: Prepared statements used
- **Foreign Key Constraints**: Data integrity maintained

### Best Practices

```java
// Example: Always use prepared statements
String sql = "SELECT * FROM transactions WHERE user_id = ?";
PreparedStatement pstmt = conn.prepareStatement(sql);
pstmt.setInt(1, userId); // Safe from SQL injection
```

---

## 📤 Export Formats

### CSV Export

**Format:**
```csv
Date,Type,Category,Description,Amount
2025-01-15,Expense,Food,"Grocery shopping",45.50
2025-01-14,Income,Salary,"Monthly salary",3000.00
```

**Features:**
- UTF-8 encoding
- Comma-separated values
- Quoted descriptions
- Date format: YYYY-MM-DD

### Excel Export

**Features:**
- XLSX format (Excel 2007+)
- Formatted columns
- Auto-width adjustment
- Headers in bold

---

## 🐛 Troubleshooting

### Common Issues

**Issue**: `java.sql.SQLException: Access denied for user`
```
Solution: Check MySQL credentials in code
- Verify DB_USER and DB_PASSWORD
- Ensure MySQL user has necessary permissions
```

**Issue**: `ClassNotFoundException: com.mysql.cj.jdbc.Driver`
```
Solution: Add MySQL connector dependency
- Ensure mysql-connector-java is in pom.xml
- Run: mvn clean install
```

**Issue**: `Module javafx.controls not found`
```
Solution: Verify JavaFX setup
- Check JavaFX version compatibility
- Ensure --module-path is correct
- Use Maven dependencies instead
```

**Issue**: Charts not displaying
```
Solution: Check JFreeChart dependency
- Ensure jfreechart is in pom.xml
- Alternative: Use JavaFX built-in charts (already implemented)
```

**Issue**: Database connection timeout
```
Solution: Check MySQL service
- Verify MySQL is running: sudo service mysql status
- Check firewall settings
- Verify connection URL
```

---

## 🔧 Configuration

### Database Configuration

**Location**: `FiscalForgeApp.java`

```java
// Configure these constants
private static final String DB_URL = "jdbc:mysql://localhost:3306/fiscalforge";
private static final String DB_USER = "root";
private static final String DB_PASSWORD = "your_password";
```

### Application Settings

**Window Size:**
```java
primaryStage.setWidth(1200);  // Default width
primaryStage.setHeight(800);  // Default height
```

**Categories:**
Edit in `showAddTransactionDialog()` method:
```java
categoryBox.getItems().addAll(
    "Food", "Transport", "Entertainment",
    "Bills", "Shopping", "Salary", "Other"
);
```

---

## 📊 Features Showcase

### File I/O
- ✅ CSV file export
- ✅ Excel file generation
- ✅ File chooser dialogs
- ✅ Error handling

### Data Visualization
- ✅ Pie charts (expense categories)
- ✅ Line charts (monthly trends)
- ✅ Interactive charts
- ✅ Color-coded visualizations

### Authentication
- ✅ User registration
- ✅ Login system
- ✅ Password hashing (SHA-256)
- ✅ Session management

### SQL Integration
- ✅ MySQL database
- ✅ CRUD operations
- ✅ Foreign key relationships
- ✅ Prepared statements
- ✅ Transaction management

---

## 🚀 Future Enhancements

### Planned Features

- [ ] **Advanced Reports**
  - PDF export
  - Custom date ranges
  - Tax reports

- [ ] **Budget Alerts**
  - Email notifications
  - Desktop notifications
  - Overspending warnings

- [ ] **Data Backup**
  - Automatic backups
  - Cloud sync
  - Import/Export user data

- [ ] **Multi-Currency**
  - Currency conversion
  - Multiple currency support
  - Exchange rate tracking

- [ ] **Recurring Transactions**
  - Set up recurring expenses
  - Automatic transaction creation
  - Subscription tracking

- [ ] **Mobile App**
  - Android/iOS companion app
  - Cloud synchronization
  - Mobile-optimized UI

---

## 🤝 Contributing

### How to Contribute

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

### Code Style

- Follow Java naming conventions
- Use meaningful variable names
- Add Javadoc comments
- Keep methods focused and small

---

## 📜 License

MIT License

Copyright (c) 2025 Michael Semera

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction.

**THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND.**

---

## 🙏 Acknowledgments

- **JavaFX** - Modern UI framework
- **MySQL** - Reliable database
- **Apache POI** - Excel file handling
- **Maven** - Dependency management

---

## 📞 Contact & Support

For questions, suggestions, or collaboration opportunities:
- Open an issue on GitHub
- Email: michaelsemera15@gmail.com
- LinkedIn: [Michael Semera](https://www.linkedin.com/in/michael-semera-586737295/)

For issues or questions:
- Review this documentation
- Check troubleshooting section
- Ensure proper privileges and setup
- Verify libpcap installation

**Author**: Michael Semera  
**Project**: FiscalForge  
**Version**: 1.0  
**Year**: 2025

### Getting Help

1. Check this README
2. Review troubleshooting section
3. Verify all dependencies installed
4. Check database connection

---

**Thank you for using FiscalForge!**

*Track expenses. Achieve goals. Build wealth.* 💰

---

**© 2025 Michael Semera. All Rights Reserved.**

*Built with ☕ for better financial management.*

---