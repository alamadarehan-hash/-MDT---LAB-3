# 📚 Library Management System (Dart)

A simple console-based Library Management System developed using **Dart**. This project demonstrates Object-Oriented Programming (OOP) concepts and asynchronous programming through basic library operations such as adding, viewing, borrowing, and returning books.

## 📌 Project Overview

The Library Management System simulates a basic library environment where users can manage books and process borrowing and returning transactions.

The application uses Dart classes, inheritance, abstraction, mixins, constructors, and asynchronous functions to demonstrate programming concepts covered in the course.

## ✨ Features

- **Add Books** – Add new books with their title and author.
- **View Books** – Display all registered books and their availability.
- **Borrow Books** – Borrow available books using their Book ID.
- **Return Books** – Return previously borrowed books.
- **Book Availability** – Automatically updates book status.
- **Activity Logging** – Displays activities performed in the system.
- **Asynchronous Operations** – Simulates processing delays when borrowing and returning books.
- **Error Handling** – Handles invalid Book IDs and unavailable books.

## 🛠️ Technologies Used

- **Programming Language:** Dart
- **Application Type:** Console-Based Application
- **Compiler:** Online Dart Compiler / Dart SDK

## 📖 OOP Concepts Implemented

| Concept | Implementation |
|---|---|
| Classes and Objects | `Book`, `Library`, and `LibraryMember` |
| Inheritance | `Book` extends `LibraryItem` |
| Abstraction | `LibraryItem` abstract class |
| Mixins | `ActivityLogger` |
| Constructors | Used to initialize objects |
| Methods | Book management and transaction operations |

## ⚡ Asynchronous Programming

This project also demonstrates asynchronous programming using:

- `Future<void>` – Defines asynchronous operations.
- `async` – Declares asynchronous functions.
- `await` – Waits for asynchronous operations to complete.
- `Future.delayed()` – Simulates a two-second processing delay.
- `try-catch` – Handles errors during borrowing and returning transactions.

## 🚀 How to Run

### Option 1: Using an Online Dart Compiler

1. Visit [DartPad](https://dartpad.dev/).
2. Open a Dart project or editor.
3. Copy the source code from `library_management_simulator.dart`.
4. Paste it into the editor.
5. Run the program.

**Note:** This application uses `dart:io` for interactive console input. If your online compiler does not support standard input (stdin), use an online Dart compiler that supports interactive console input.

### Option 2: Using Dart SDK

1. Install the [Dart SDK](https://dart.dev/get-dart).
2. Clone this repository:

   ```bash
   git clone https://github.com/alamadarehan-hash/-MDT---LAB-3
   ```

3. Navigate to the project directory:

   ```bash
   cd YOUR-REPOSITORY
   ```

4. Run the application:

   ```bash
   dart run library_management_simulator.dart
   ```

## 🖥️ Application Menu

```text
====================================
       LIBRARY MANAGEMENT SYSTEM
====================================
Welcome, Student!

--------------- MENU ---------------
1. Add a Book
2. View All Books
3. Borrow a Book
4. Return a Book
5. Exit

Enter your choice:
```

## 📂 Project Structure

```text
Library-Management-System/
│
├── library_management_simulator.dart
└── README.md
```

## 🎯 Project Objectives

- Apply Object-Oriented Programming concepts using Dart.
- Understand inheritance, abstraction, and mixins.
- Implement asynchronous operations using Future, async, and await.
- Practice error handling using try-catch.
- Develop a functional console-based application.

## 🎓 Project Information

**Project Title:** Library Management System (Dart App Simulator)

**Project Type:** Individual Final Midterm Project

**Programming Language:** Dart

**Course Coverage:** Weeks 7–11

## 👨‍💻 Author

Developed as an academic programming project to demonstrate the application of Dart OOP and asynchronous programming concepts.

---

*This project is intended for educational purposes and demonstrates basic library management functionality.*
