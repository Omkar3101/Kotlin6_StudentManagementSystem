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
git clone https://github.com/Omkar3101/Kotlin6_StudentManagementSystem.git

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
//Student Management System Using OOPs

//Create a Student Mangement System where you can add, view, and update student details using Classes, Objects, Methods, and Constructors in Kotlin.

/*
Features of the Project:
1. Add new students (Name, Age, Roll Number, Marks)
2. View all students' details.
3. Find a student by Roll Number.
4. Update a student's marks.
5. Delete a student record
 */

//1. Create a Student Class
class Student(val rollNumber: Int, var name: String, var age: Int, var marks: Double) {
    fun displayStudent() {
        println("Roll No: $rollNumber | Name: $name | Age: $age | Marks: $marks")
    }
}

//2. Create a StudentDatabase Class
class StudentDatabase {
    private val students = mutableListOf<Student>()

    fun addStudent(student: Student) {
        students.add(student)
        println("${student.name} added successfully!")
    }

    fun viewStudents() {
        if (students.isEmpty()) {
            println("No students found!")
        } else {
            students.forEach { it.displayStudent()}
        }
    }

    fun findStudent(rollNumber: Int): Student? {
        return students.find{ it.rollNumber == rollNumber }
    }

    fun updateMarks(rollNumber: Int, newMarks: Double) {
        val student = findStudent(rollNumber)
        if (student != null) {
            student.marks = newMarks
            println("Marks updated for ${student.name}")
        } else{
            println("Student not found!")
        }
    }

    fun deleteStudent (rollNumber: Int) {
        val student = findStudent(rollNumber)
        if (student != null) {
            students.remove (student)
            println("${student.name} removed successfully!")
        } else {
            println("Student not found!")
        }
    }
}

//3. Main Function to Run the System
fun main() {
    val database = StudentDatabase()

    while (true) {
        println("\n Student Management System")
        println("1. Add Student")
        println("2. View Student")
        println("3. Update Marks")
        println("4. Delete Student")
        println("5. Exit")
        print("Choose an option: ")

        when (readLine()?.toIntOrNull()) {
            1 -> {
                print("Enter Roll No: ")
                val rollNumber = readLine()?.toIntOrNull()?:0
                print("Enter Name: ")
                val name = readLine()?:""
                print("Enter Age: ")
                val age = readLine()?.toIntOrNull()?:0
                print("Enter Marks: ")
                val marks = readLine()?.toDoubleOrNull()?:0.0

                val student = Student(rollNumber, name, age, marks)
                database.addStudent(student)
            }
            2 -> database.viewStudents()
            3 -> {
                print("Enter Roll No: ")
                val rollNumber = readLine()?.toIntOrNull()?:0
                print("Enter New Marks: ")
                val newMarks = readLine()?.toDoubleOrNull()?:0.0

                database.updateMarks(rollNumber, newMarks)
            }
            4 -> {
                print("Enter Roll No to Delete: ")
                val rollNumber = readLine()?.toIntOrNull()?:0

                database.deleteStudent((rollNumber))
            }
            5 -> {
                println("Existing...")
                break
            }
            else -> println("Invalid option! Try again.")
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


