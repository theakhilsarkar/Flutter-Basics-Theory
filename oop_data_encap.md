
# Object-Oriented Programming (OOP) in Dart

This document provides an overview of Object-Oriented Programming (OOP) concepts in Dart, suitable for study and interview preparation.

## Introduction

OOP is a programming paradigm that emphasizes organizing code into reusable, structured, and secure units called objects.

## Key Concepts

### 1. Class

-   A blueprint or template for creating objects.
-   Defines the attributes (data) and methods (behavior) that objects of that class will have.
-   Acts as a user-defined data type (model class).

### 2. Object

-   An instance of a class.
-   Used to access the methods and attributes defined in the class.
-   Represents a specific entity based on the class's blueprint.

## Four Pillars of OOP

### 1. Data Encapsulation

-   **What:** Bundling data (attributes) and methods that operate on that data into a single unit (class).
-   **Why:**
    -   Improves code organization and structure.
    -   Enhances data security by controlling access to attributes.
    -   Promotes code reusability.
-   **How:** By defining attributes and methods within a class, and controlling access using access modifiers (e.g., public, private).

### 2. Inheritance

-   **What:** Creating new classes (derived or child classes) from existing classes (base or parent classes).
-   **Why:**
    -   Enables code reuse by inheriting attributes and methods from the parent class.
    -   Supports the "is-a" relationship (e.g., a "Dog" is-a "Animal").
    -   Promotes code extensibility.
-   **How:** Using the `extends` keyword to create a subclass.

### 3. Polymorphism

-   **What:** The ability of an object to take on many forms.
-   **Why:**
    -   Allows for writing generic code that can work with objects of different classes.
    -   Enhances code flexibility and maintainability.
-   **How:** Through method overriding (providing a different implementation in the subclass). Dart does not support method overloading.

### 4. Data Abstraction

-   **What:** Hiding complex implementation details and showing only the essential features of an object.
-   **Why:**
    -   Simplifies the user's interaction with objects.
    -   Reduces complexity by focusing on what an object does rather than how it does it.
-   **How:** Using abstract classes and interfaces.

## Example: Data Encapsulation

```dart
class Area {
  int? height; // Attribute (data)
  int? width;  // Attribute (data)

  // Method (behavior)
  (int?, int?) calculateArea(int height, int width) {
    this.height = height;
    this.width = width;
    return (this.height, this.width); // Returning multiple values using a tuple
  }
}

void main() {
  // Creating an object of the Area class
  Area areaObject = Area();

  // Calling the calculateArea method and storing the returned tuple
  var areaValues = areaObject.calculateArea(10, 20);

  // Accessing the values from the tuple
  print("Height: ${areaValues.$1}");
  print("Width: ${areaValues.$2}");
}
```

## Key Points for Interviews

-   Explain the four pillars of OOP (encapsulation, inheritance, polymorphism, abstraction) with examples.
-   Differentiate between a class and an object.
-   Explain the `this` keyword and its usage.
-   Understand the concept of null safety (`?` operator) and the `late` keyword in Dart.
-   Be prepared to discuss method overriding and its importance in polymorphism.
-   Explain the concept of data hiding and access modifiers (if applicable).
-   Understand the difference between `var` and `dynamic` in Dart.
-   Dart does not support method overloading.
```
-------------------------------------original version----------------------------------------------------------------------------------

```markdown
# OOPs in Dart
# Object Oriented Programming

OOPs is programming paradigm(concept,method,way) to make code
structurized, organized, secure and reuseable.

oop is class and object based concept to progarm anything.

## class :
1. class is collection of methods and attributes.
2. class is a blueprint or template to craeting object.
3. class is user define datatype. : modal class.

## object :
1. object is used to access methods and attributes declared in the class.
2. object is an instance/representative of class.
3. object is one type of variable which follow class as a blueprint.

## OOP Pillars:

1. Data Encapsualtion
2. Inheritance
3. Polymorphism
4. Data Abstracion

## what, why and how

## 1. Data Encapsualtion : structrize, organize & reuseable
-> We encapsulate/add/pack method and attribute in same class in defferent units
where we declare methods and attributes saperately to ease of access.

-> we can easily understand coding structure & access as per need.
-> by encapsulation our code become structurize, organize and reuseable.

-> we declared same behavioural attribute and methods in same class.
-> we keep attributes and methods in defferent units in the class.
-> we can create multiple objects of same class to access methods and attributes of the class.

```dart
class Area // class name always start from capital letter
{
  int? height, width; // variables declared in the class called as attributes.
  // ? we have to put null operator when we declare attribute in the class.
  // or else we can use late keyword to specify or confirmation value will must initialize.
  // late : if value not initilize in late define variable, it will throw a error: late initialization in attribute.

  (int?, int?) areaOfRectangle(int height, int width) {
    // if we not specify datatype in params, it will become dynamic
    this.height = height;
    this.width = width;
    // this : to define global attribute & methods in the class
    return (
      this.height,
      this.width
    ); // we can return multiple values - but specify return type as well
  }
}

//datatype variable = value;
// className obj = Class();

void main() {
  // Area a1 = Area();
  // var data = a1.areaOfRectangle(10, 20);
  // print(data.$1);
  // print(data.$2);

  // int a, b;
  // (a!, b!) = a1.areaOfRectangle(10, 20);
  // print(a);
  // print(b);

  // var a1 = Area(); // it fix type of first assign value
  // dynamic a2 = Area(); // its dynamic, can accept all type of value.
}
