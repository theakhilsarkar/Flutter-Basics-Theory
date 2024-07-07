

## Additional Programming Concepts

### Class
- A user-defined datatype and blueprint for creating objects.
- A class is a collection of methods and attributes.
  
### Primitive and Non-Primitive Datatypes
- Primitive Datatypes: int, float, double, bool
- Non-Primitive Datatypes: array, List, Map, Set, String

### Nullable and Null-aware Operators
- ? Nullable operator: Indicates that a variable or object can be null.
- ! Null-aware operator: Ensures that a value will be present.

```markdown
# Flutter Application

This project demonstrates the basics of a Flutter application. 

## Main Function

The `main` function initializes the Flutter application.

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}
```

## Object-Oriented Programming (OOP) in Flutter

### Widgets
- Everything is a widget in Flutter.
- Every individual part of the UI is a widget.
- Multiple widgets make up a page/screen.
- Multiple pages/screens make up an application.

### Naming Conventions
- Every method/user-defined function/member function should start with a small letter and follow camelCase.
- Every class should start with a capital letter and follow CamelCase.
- In Flutter, every widget is a class.

### Widget Classification
- If any class is a part of the UI, it is a widget.
- If any class plays a supportive role with a widget or provides any functionality, it is not necessarily a widget.

### Types of Widgets
1. **Built-in Widgets**: Already defined in the library.
2. **User-defined Widgets**: Created by the user as per need.

## Flutter Concepts

### State
State is a type of data used in the UI.

### Static
Static means the data will not update/change/modify.

### Types of Widgets

1. **StatefulWidget**:
   - The state can be changed, making the UI dynamic.
   - Uses more memory compared to a StatelessWidget.

2. **StatelessWidget**:
   - The state is static.
   - Uses less memory compared to a StatefulWidget.

## Widget Interactions
- Widgets can connect with other widgets.
- `BuildContext`: Provides information about widgets in the widget tree and the sizing of the device.

## OOP Principles in Flutter

- **Inheritance**: To get all features and functionality of a stateless widget.
- **Data Abstraction**: The `build` method is an abstract method of the `StatelessWidget` class, so it must be declared in the child class.
- **Polymorphism**: The `build` method is created in the parent class and overridden in the child class.
- **Method Overriding**: When the parent class and child class have methods with the same name.

## Example: MyApp Widget

```dart

import 'package:flutter/material.dart';

class MyApp extends StatelessWidget {
  const MyApp({super.key}); // const constructor

  // super keyword is used to access attributes/method of parent class in child class.
  @override // notation for method overriding
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: Scaffold(),
    );
  }
}
```

# Constructors in Dart

In Dart, constructors are special methods used to initialize the attributes of a class. This document provides an overview of different types of constructors in Dart, using a `Movie` class as an example.

## Movie Class Example


```markdown

```dart
class Movie {
  late String name, date, gener;

  - Default Constructor
  Movie() {
    print("Today BOX OFFICE");
  }

  - Named Constructor
  Movie.set({
    required String name,
    required String date,
    required String gener,
  }) {
    this.name = name;
    this.date = date;
    this.gener = gener;
  }

  - Factory Constructor
  factory Movie.cinema() {
    return Movie.set(
        name: "Pushpa 2", date: "12-12-2012", gener: "Action/Crime");
  }

  - Method to print movie details
  void releaseMovie() {
    print("Movie name : $name");
    print("Release Date : $date");
    print("Movie Gener : $gener");
  }
}

```

### Types of Constructors

#### Default Constructor
- The default constructor is used to initialize attributes with default values or to execute a specific code block when an object is created.
- In the example, the default constructor prints a message when a `Movie` object is created.

```dart
Movie() {
  print("Today BOX OFFICE");
}
```

#### Named Constructor
- Named constructors provide a way to create multiple constructors in a class, each with a different name.
- They are used to initialize attributes with specific values.

```dart
Movie.set({
  required String name,
  required String date,
  required String gener,
}) {
  this.name = name;
  this.date = date;
  this.gener = gener;
}
```

#### Factory Constructor
- Factory constructors can return an instance of the current class.
- They are used to control the instance creation process and can return existing instances instead of always creating new ones.

```dart
factory Movie.cinema() {
  return Movie.set(
      name: "Pushpa 2", date: "12-12-2012", gener: "Action/Crime");
}
```

## Method Example

The `releaseMovie` method in the `Movie` class prints the details of a movie.

```dart
void releaseMovie() {
  print("Movie name : $name");
  print("Release Date : $date");
  print("Movie Gener : $gener");
}
```
