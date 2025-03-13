# Student Management System

A simple Student Management System built using Kotlin that allows adding, viewing, and managing student records. This project is part of my Kotlin learning journey and focuses on implementing object-oriented programming (OOP) concepts.

## Features
1. Add new students with name, age, and ID.
2. View all students in a structured format.
3. Search for a student by ID.
4. Remove a student from the system.
5. Beginner-friendly Kotlin project using Classes & Objects.


## Technologies Used
1. Kotlin
2. IntelliJ IDEA



## How to Run the Project?

* Clone the Repository
git clone https://github.com/Omkar3101/Kotlin_StudentManagementSystem.git

* Open in IntelliJ IDEA
Select Open Project and navigate to the cloned repository

* Run the Project
Open Main.kt file

* Click on Run or use Shift + F10

* Use the Student Management System
1. Select an option: Add Student, View Students, Search, or Remove Student
2. Enter student details when prompted.
3. View and manage student records dynamically.

* Code Overview

``` kotlin
class Student(val id: Int, val name: String, val age: Int)

class StudentManager {
    private val students = mutableListOf<Student>()

    fun addStudent(id: Int, name: String, age: Int) {
        students.add(Student(id, name, age))
        println("Student added successfully!")
    }

    fun viewStudents() {
        if (students.isEmpty()) {
            println("No students found.")
        } else {
            println("Student List:")
            students.forEach { println("ID: ${it.id}, Name: ${it.name}, Age: ${it.age}") }
        }
    }

    fun searchStudent(id: Int) {
        val student = students.find { it.id == id }
        if (student != null) {
            println("Student Found: ID: ${student.id}, Name: ${student.name}, Age: ${student.age}")
        } else {
            println("Student not found.")
        }
    }

    fun removeStudent(id: Int) {
        val removed = students.removeIf { it.id == id }
        if (removed) {
            println("Student removed successfully.")
        } else {
            println("Student not found.")
        }
    }
}

fun main() {
    val manager = StudentManager()
    while (true) {
        println("\nChoose an option: 1) Add Student  2) View Students  3) Search Student  4) Remove Student  5) Exit")
        when (readLine()?.toIntOrNull()) {
            1 -> {
                print("Enter ID: ")
                val id = readLine()?.toIntOrNull() ?: 0
                print("Enter Name: ")
                val name = readLine() ?: ""
                print("Enter Age: ")
                val age = readLine()?.toIntOrNull() ?: 0
                manager.addStudent(id, name, age)
            }
            2 -> manager.viewStudents()
            3 -> {
                print("Enter Student ID to search: ")
                val id = readLine()?.toIntOrNull() ?: 0
                manager.searchStudent(id)
            }
            4 -> {
                print("Enter Student ID to remove: ")
                val id = readLine()?.toIntOrNull() ?: 0
                manager.removeStudent(id)
            }
            5 -> break
            else -> println("Invalid choice, try again.")
        }
    }
}
```

## Future Improvements
* Store student data in a file or database for persistence
* Add a GUI version for better user experience
* Implement sorting and filtering features


## License
This project is licensed under the MIT License – see the LICENSE file for details.

## Let's Connect

LinkedIn

GitHub


