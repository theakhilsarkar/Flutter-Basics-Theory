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

```markdown

# Flutter Container Widget Example

This Flutter application demonstrates the use of the `Container` widget to create custom shapes with various properties like height, width, decoration, padding, margin, and alignment.

## Code Explanation

### Main Application

The main application consists of a stateless widget (`MyApp`) that sets up the `MaterialApp` and a stateful widget (`HomePage`) that contains the `Container`.

```dart
import 'package:flutter/material.dart';

// Parent widget : user-defined
class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      debugShowCheckedModeBanner: false,
      home: HomePage(), // Home: attach screens here
    );
  }
}
```

### Home Page

The `HomePage` widget is a stateful widget that contains a `Scaffold` with an `AppBar` and a centered `Container` widget.

```dart
// Home page widget
class HomePage extends StatefulWidget {
  const HomePage({super.key});

  @override
  State<HomePage> createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        leading: const Icon(Icons.menu),
        title: const Text('Home Page'),
      ),
      body: Center(
        child: Container(
          height: 100,
          width: 300,
          alignment: Alignment.center,
          decoration: const BoxDecoration(
            color: Colors.green,
            borderRadius: BorderRadius.vertical(
              top: Radius.circular(10),
              bottom: Radius.circular(10),
            ),
            border: Border.symmetric(
              vertical: BorderSide(width: 2),
            ),
            gradient: LinearGradient(colors: [
              Colors.deepOrange,
              Colors.white,
              Colors.green,
            ]),
          ),
          child: Container(
            height: 50,
            width: 50,
            color: Colors.amber,
          ),
        ),
      ),
    );
  }
}
```

### Container Properties

- **child**: Connects another widget within the container.
- **height** and **width**: Define the height and width of the container.
- **decoration**: Used to decorate the container with properties like color, border, shadow, and border radius.
- **padding**: Inner spacing within the container.
- **margin**: Outer spacing outside the container.
- **alignment**: Aligns the child widget within the container.

### BoxDecoration Properties

- **color**: Sets the background color of the container.
- **borderRadius**: Creates rounded corners for the container. In this example, the container has a vertical border radius of 10 at the top and bottom.
- **border**: Defines the border of the container. Here, a symmetric border with a vertical border side width of 2 is used.
- **gradient**: Applies a linear gradient background to the container. The gradient transitions through deep orange, white, and green colors.

### Inner Container

The inner container demonstrates nesting of containers by setting height, width, and background color.


### ----------------------------------------------------------------------------------------------------------------------------
Certainly! Below is the readme formatted code explaining the given Flutter widget:

```markdown
# Flutter GestureDetector with Custom Container Example

This example demonstrates the use of the `GestureDetector` widget to handle tap gestures on a custom-designed `Container` widget. The container is centered and styled as a circular button with shadows.

## Code Explanation

### Widget Structure

This example uses an `Align` widget to center a `GestureDetector` containing a `Container` widget with custom styling.

```dart
Align(
  alignment: Alignment.center,
  child: GestureDetector(
    onTap: () {
      print("button pressed !");
    },
    child: Container(
      alignment: Alignment.center,
      child: Text(
        'ON',
        style: TextStyle(color: Colors.white),
      ),
      height: 150,
      width: 150,
      decoration: BoxDecoration(
        color: Colors.black,
        shape: BoxShape.circle,
        boxShadow: [
          BoxShadow(
            color: Colors.green,
            spreadRadius: 10,
            blurRadius: 25,
          ),
        ],
      ),
    ),
  ),
)
```

### Align Widget

- **alignment**: Sets the alignment of the child widget within the parent. Here, it centers the `GestureDetector` widget.

### GestureDetector Widget

The `GestureDetector` widget detects various gestures, such as taps, drags, and swipes.

- **onTap**: A callback function that is called when the widget is tapped. In this example, it prints "button pressed !" to the console.

### Container Widget

The `Container` widget is used to create a custom-styled button.

- **alignment**: Centers the text within the container.
- **child**: Contains a `Text` widget with the text "ON" and a white color.
- **height** and **width**: Sets the dimensions of the container to 150x150.
- **decoration**: Customizes the appearance of the container.

### BoxDecoration Properties

- **color**: Sets the background color of the container to black.
- **shape**: Sets the shape of the container to a circle using `BoxShape.circle`.
- **boxShadow**: Adds shadow effects to the container.

  - **color**: Sets the shadow color to green.
  - **spreadRadius**: The amount the shadow will spread.
  - **blurRadius**: The blur radius of the shadow.

### Usage

To run this code, place it in the appropriate build method of a widget in your Flutter project and execute the app using `flutter run`.

```shell
flutter run
```

This will start the application and display a centered, circular button with text "ON". Tapping the button will trigger the `onTap` callback, printing a message to the console.
```

This readme code provides a clear and detailed explanation of the given widget, ensuring that users can understand and utilize the example with ease.

Certainly! Below is the readme formatted code that explains the given Flutter widget and its properties:

```markdown
# Flutter Container with SingleChildScrollView and FloatingActionButton Example

This example demonstrates the use of a `Container` widget with horizontal scrolling capabilities provided by `SingleChildScrollView` and the use of a `FloatingActionButton` to update the state in a `StatefulWidget`.

## Code Explanation

### Container with SingleChildScrollView

The `Container` widget is styled with a background color and contains a horizontally scrollable `Row` of widgets.

```dart
Container(
  color: Colors.green.shade200,
  child: SingleChildScrollView(
    scrollDirection: Axis.horizontal,
    child: Row(
      children: [
       // all widgets will be here....
      ],
    ),
  ),
)
```

- **color**: Sets the background color of the container.
- **SingleChildScrollView**: Enables scrolling for a single child widget.
  - **scrollDirection**: Sets the scrolling direction to horizontal.
  - **Row**: Arranges its children in a horizontal line.

### FloatingActionButton

The `FloatingActionButton` widget provides a button that performs an action when pressed. In this example, it increments a counter and prints its value.

```dart
floatingActionButton: FloatingActionButton(
  onPressed: () {
    setState(() {
      count++;
    });
    print(count);
  },
  backgroundColor: Colors.white,
  child: Icon(Icons.add),
)
```

- **onPressed**: A callback function that is called when the button is pressed.
  - **setState**: Used to update the state of the widget and rebuild the UI.
  - **count++**: Increments the counter variable.
  - **print(count)**: Prints the current value of the counter to the console.
- **backgroundColor**: Sets the background color of the button to white.
- **child**: Contains an `Icon` widget to display an add icon.

### Additional Explanations

#### Hot Reload and Hot Restart

- **Hot Reload**: Rebuilds the UI without restarting the application. The state is preserved.
- **Hot Restart**: Restarts the entire application. The state is reset.

#### Functions

- **Function as an Expression**: A single line function that returns a value.
  ```dart
  int sum(int a, int b) => a + b;
  ```
- **Anonymous Function**: A function without a name.
  ```dart
  () {
    // code
  }
  ```

### Row and Column Widgets

- **Row**: Arranges its children horizontally.
  - **children**: A list of widgets to display in a row.
  - **default width**: Maximum width available.
  - **default height**: Height based on content.
- **Column**: Arranges its children vertically.
  - **children**: A list of widgets to display in a column.
  - **default height**: Maximum height available.
  - **default width**: Width based on content.

### Usage

To run this code, place it in the appropriate build method of a widget in your Flutter project and execute the app using `flutter run`.

```shell
flutter run
```

This will start the application and display a container with horizontally scrollable content and a floating action button to increment and display a counter.
```

This readme code provides a clear and detailed explanation of the given widget, ensuring that users can understand and utilize the example with ease.
