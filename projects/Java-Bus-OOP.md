---
layout: project
type: project
image: img/Java_programming_language_logo.svg.png
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
<img width="400px" height="220px" src="../img/360_F_411710211_Np9uD5XpXlGIQ9gzIWYunuckaBaGK7YY.jpg" class="img-thumbnail" >
This was an assignment I had to fulfill to gain an understanding of the basics of object oriented programmin for Java. I displayed the concepts of inheritence and 
using functions from encapsulated objects in a driver file. This was my first forray into programming, the project was divided into three separate files in the 
directory, a file for the student object, bus object, and the driver file that uses these classes in a command line user interactive experience.

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
    public String toString(){
        return "";
    }
}
```
