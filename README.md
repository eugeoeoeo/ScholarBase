# Student Record Management System

A JavaFX desktop application for managing student records with full CRUD (Create, Read, Update, Delete) functionality, connected to a PostgreSQL database.

## Technologies Used

- **Java 21**
- **JavaFX 21** – GUI framework
- **SceneBuilder** – FXML-based GUI design
- **JDBC** – Database connectivity
- **PostgreSQL** – Relational database
- **Maven** – Build and dependency management

## Features

- Add new student records
- Display all records in a TableView
- Update selected student records
- Delete selected student records
- Clear input fields
- Input validation (no empty fields)
- Year level selection via ChoiceBox (Enum-based)

## Project Structure

```
src/main/java/com/example/demo/
├── MainApp.java          # Application entry point
├── Controller.java       # CRUD operations and UI logic
├── Student.java          # Model class with JavaFX properties
├── YearLevel.java        # Enum for year level choices
└── DBConnection.java     # PostgreSQL JDBC connection

src/main/resources/com/example/demo/
└── main.fxml             # GUI layout (SceneBuilder)
```

## Database Setup

### 1. Create the database

```sql
CREATE DATABASE studentdb;
```

### 2. Create the students table

```sql
CREATE TABLE students (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    course VARCHAR(50),
    year_level VARCHAR(50)
);
```

### 3. Update the connection credentials

In `DBConnection.java`, update the password to match your PostgreSQL credentials:

```java
return DriverManager.getConnection(
    "jdbc:postgresql://localhost:5432/studentdb",
    "postgres",
    "your_password"
);
```

## How to Run

1. Clone the repository
2. Set up the PostgreSQL database (see above)
3. Open the project in IntelliJ IDEA
4. Make sure Maven dependencies are loaded
5. Run `MainApp.java`

## Dependencies

| Dependency | Version |
|---|---|
| JavaFX Controls | 21.0.6 |
| JavaFX FXML | 21.0.6 |
| PostgreSQL JDBC Driver | 42.7.3 |
