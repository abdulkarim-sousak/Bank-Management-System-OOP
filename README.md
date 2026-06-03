# 🏦 Bank Management System (C++)

## Overview

This project is a **Bank Management System** developed in **C++** using **Object-Oriented Programming (OOP)** principles. The application provides a console-based interface for managing bank clients, user accounts, authentication, transactions, and administrative operations.

The project follows a layered design where the **business logic is separated from the user interface**, making the code easier to maintain, extend, and test.

---

# Technologies Used

- C++
- Object-Oriented Programming (OOP)
- File Handling (Text Files)
- Visual Studio Project Structure
- Console User Interface

---

# Object-Oriented Programming Concepts

The project heavily relies on OOP concepts:

## 1. Encapsulation

Data and behavior are grouped inside classes.

Examples:

- `clsBankClient`
- `clsUser`
- `clsPerson`
- `clsDate`
- `clsString`
- `clsUtil`

Private data members are protected from direct access and manipulated through class methods.

---

## 2. Inheritance

The project uses inheritance to reduce code duplication.

Example:

```cpp
class clsBankClient : protected clsPerson
```

```cpp
class clsUser : protected clsPerson
```

Both classes inherit common personal information such as:

- First Name
- Last Name
- Email
- Phone Number

from the base class `clsPerson`.

---

## 3. Abstraction

Complex implementation details are hidden behind simple interfaces.

Example:

- Finding clients
- Loading data from files
- Saving records
- Performing transactions

The user interacts with high-level screens without knowing how the data is processed internally.

---

## 4. Polymorphism

The project architecture allows future extension and customization through inherited screen classes and shared interfaces.

---

# Separation of Logic from User Interface

One of the strongest aspects of this project is the separation between:

## Presentation Layer (UI)

Responsible for displaying information and interacting with the user.

Examples:

- `clsLoginScreen`
- `clsMainScreen`
- `clsClientListScreen`
- `clsAddNewClientScreen`
- `clsDeleteClientScreen`
- `clsUpdateClientScreen`
- `clsFindClientScreen`
- `clsTransactionsScreen`
- `clsManageUsersScreen`
- `clsUsersListScreen`

These classes focus only on:

- Printing menus
- Reading user input
- Calling business logic methods

---

## Business Layer

Responsible for handling application rules and data operations.

Examples:

- `clsBankClient`
- `clsUser`
- `clsDate`
- `clsString`
- `clsInputValidate`
- `clsUtil`

These classes contain:

- Validation logic
- File operations
- Data manipulation
- Banking operations

The UI never directly manipulates file structures or internal data processing.

---

## Data Layer

The project stores data in text files:

### Clients Database

```text
Clients.txt
```

Stores:

- Client information
- Account numbers
- PIN codes
- Account balances

### Users Database

```text
Users.txt
```

Stores:

- User information
- Login credentials
- Permissions

---

# Project Architecture

```text
+-------------------------+
|      Login Screen       |
+------------+------------+
             |
             v
+-------------------------+
|      Main Screen        |
+------------+------------+
             |
     +-------+-------+
     |               |
     v               v
 Client Module   User Module
     |               |
     v               v
 Transactions   Permissions
     |
     v
 File Storage
```

---

# Main Features

## Authentication System

- Login screen
- Username validation
- Password validation
- User permission control

Implemented mainly through:

- `clsLoginScreen`
- `clsUser`

---

## Client Management

Users can:

- View all clients
- Add new clients
- Update client information
- Delete clients
- Search for clients

Implemented through:

- `clsBankClient`
- Client screen classes

---

## Transaction Management

Supported operations:

- Deposit
- Withdraw
- Balance management
- Total balances report

Implemented through:

- `clsTransactionsScreen`
- `clsDepositeScreen`
- `clsWithdrawScreen`
- `clsTotalBalancesScreen`

---

## User Management

Administrators can:

- Add users
- Delete users
- Update users
- Search users
- Manage permissions

Implemented through:

- `clsManageUsersScreen`
- `clsAddNewUserScreen`
- `clsDeleteUserScreen`
- `clsUpdateUserScreen`
- `clsFindUserScreen`

---

# Validation System

Input validation is centralized inside:

```cpp
clsInputValidate
```

Responsibilities:

- Number validation
- Range validation
- Safe user input

This prevents duplicated validation code across screens.

---

# Utility Classes

## clsString

Provides string helper functions such as:

- Split
- Parsing
- String manipulation

## clsDate

Handles date-related operations.

## clsUtil

Contains reusable utility functions used throughout the project.

---

# Advantages of the Design

### Maintainability

Each class has a clear responsibility.

### Scalability

New screens and features can be added with minimal changes.

### Reusability

Utility and business classes can be reused in other projects.

### Readability

The code structure is organized and easy to understand.

### Security

Permission-based access control restricts unauthorized operations.

---

# Conclusion

This Bank Management System demonstrates a solid application of Object-Oriented Programming principles in C++. The project separates the user interface from the business logic, follows a modular architecture, and implements client management, transaction processing, authentication, and user administration using clean and maintainable code.

The overall design makes the application scalable, reusable, and suitable as an educational example of building a complete OOP-based banking system in C++.
"""
path = "/mnt/data/Bank_Management_System_Documentation.md"
Path(path).write_text(md, encoding="utf-8")
print(path)