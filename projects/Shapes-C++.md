---
layout: project
type: project
image: img/cotton/cotton-square.png
title: "Shapes C++ Assignment"
# All dates must be YYYY-MM-DD format!
date: 2022-04-12
published: true
labels:
  - C++
  - Inheritance
  - Programming
summary: "An assignment where I utilized inheritance in the C++ programming language to design shapes that derive from other shape classes, that in turn derive from the master shape class"
---
<img width="400px" height="220px" src="../img/jiang-ziya-1.jpg" class="img-thumbnail" >

This is an example portion of the assignment, where a circle is derived from a shape, and a sphere is derived from a circle
```cpp
class Shape {
  public:
   virtual void printDetails() const = 0;
   virtual const char* name() const = 0;
   virtual void inputData() = 0;
   virtual double area() const = 0;
   virtual double volume() const {
      return 0.0;
   }     
};   

class Circle : public Shape {
  public:
   Circle (double r = 0.0) {
      if (r<0) r=-r;
      radius = r;
   }
    
   const char* name() const{
      return "Circle";
   }
  
   void printDetails() const{
      cout << "The " << name() << "'s area = " << area() << endl;
   } 
    
   void inputData() {
      cout << "Enter the " << name() << "'s radius: ";
      cin >> radius;
      if(radius<0){
         radius = -radius;
      }
   }
    
   double area() const {
      return PI * radius * radius;
   }
   
  protected:    
   double radius;
};
class Sphere: public Circle {
    public:
        Sphere(double r):Circle(r){

        }
        Sphere():Circle(){

        }
        const char * name() const{
            return "Sphere";
        }    
  
        void printDetails() const{
            cout << "The " << name() << "'s surface area = " << area() << endl;
            cout << "The " << name() << "'s volume = " << volume() << endl;
        } 
        double area() const {
            return 4*PI * radius * radius;
        }
        double volume() const {
            return ((4*PI * radius * radius* radius)/3);
        }
};
```
