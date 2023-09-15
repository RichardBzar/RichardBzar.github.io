---
layout: project
type: project
image: img/Java_programming_language_logo.svg (2).png
title: "Java Bus Object Oriented Programming"
# All dates must be YYYY-MM-DD format!
date: 2019-08-12
published: true
labels:
  - Java
  - Object Oriented Programming
  - Commandd Line
summary: "A project from my intodution to programming class that asks us to create a bus program that functions as a regular schoolbus would"
---
<img width="200px" height="120px" src="../img/360_F_411710211_Np9uD5XpXlGIQ9gzIWYunuckaBaGK7YY.jpg" class="img-thumbnail" >

This was an assignment I had to fulfill to gain an understanding of the basics of object oriented programmin for Java. I displayed the concepts of inheritence and 
using functions from encapsulated objects in a driver file. This was my first foray into programming. The project was divided into three separate files in the 
directory, a file for the student object, bus object, and the driver file that uses these classes in a command line user interactive experience. The student object
had basic class tendencies for Java, acting as an object where a student's age and name were necessary to create a student. The private data types were 
encapsulated, only allowing access through mutaters and setters.

The bus file managed to make use of the student file in order to have a student array datatype that gives the object a way to express how many students are inside
the bus. There are also integers to represent the bus's capacity and how many are currently inside the buss. The main functions the bus has with this file is to 
add students to the bus, remove students from the bus by name, and display all the students information. The bus can't be over max occupancy otherwise the add 
student function will not add more students to teh predeclared array in the bus.

The last file, the driver file, basically just asks for user input in a text based UI hosted on the command line to access the diffrent functions of the bus file 
and display how each function operates. The user can repeatedly acces commands from the driver until entering a 0 as a response. After succesful completion, the 
driver file will signify the end of the intereaction with a thank you message.

This is the code for the student objects that are stored in the buses array property
```cpp
class Student{
    private String name;
    private int age;
    Student(int age, String name){
        this.age = age;
        this.name = name;
    }
    public int getAge(){
        return this.age;
    }
    public void setAge(int age){
        this.age = age;
    }
    public String getName(){
        return this.name;
    }
    public void setName(String name) {
        this.name = name;
    }
}
```
