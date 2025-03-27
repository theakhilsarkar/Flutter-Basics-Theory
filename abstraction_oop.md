

# **Data Abstraction and Abstract Classes in Dart**  

## **1. What is Data Abstraction?**  
Data abstraction is the process of hiding complex implementation details and exposing only the necessary functionality to the user.  
- It helps in securing data by preventing direct access to attributes and methods.  
- In Dart, private attributes and methods are declared using an underscore (`_`) and are only accessible within the same file.  

### **Example: Private Attributes in a Class**  
```dart
class Person {
  // Private attributes (cannot be accessed outside this file)
  String? _name, _age, _gender;

  // Constructor
  Person(this._name, this._age, this._gender);

  // Getter method to access private attributes
  void getDetails() {
    print("Name: $_name");
    print("Age: $_age");
    print("Gender: $_gender");
  }

  // Other methods
  void post() {}
  void update() {}
  void api() {}
}

void main() {
  var person = Person("John", "25", "Male");
  person.getDetails(); // Accessing details through a method
}
```
📌 **Key Points:**  
✅ Private attributes (`_name`, `_age`, `_gender`) cannot be accessed directly.  
✅ `getDetails()` method allows controlled access to private data.  

---

## **2. What is an Abstract Class?**  
An **abstract class** is a class that **cannot be instantiated** and is meant to be inherited by other classes.  
- It **can** have both **abstract methods** (without implementation) and **concrete methods** (with implementation).  
- To use an abstract class, we must **inherit** it in a child class and provide implementations for abstract methods.  

### **Example: Abstract Class in Dart**  
```dart
// Abstract class
abstract class A {
  // Concrete method (has implementation)
  void printA() {
    print("This is an abstract class A");
  }

  // Abstract method (without implementation)
  void absMethod();
}

// Child class inheriting abstract class
class B extends A {
  @override
  void absMethod() {
    print("This is an abstract method!");
  }
}

void main() {
  B obj = B();
  obj.printA();     // Calling concrete method
  obj.absMethod();  // Calling overridden abstract method
}
```
📌 **Key Points:**  
✅ We **cannot** create an object of an abstract class.  
✅ Abstract methods **must** be implemented in the child class.  

---

## **3. Real-World Example: Abstract Class in Flutter**  
In **Flutter**, we use abstract classes for **stateful widgets** like:  

```dart
abstract class StatefulWidget {
  int build(bool context);  // Abstract method
  void initState() {}       // Concrete method
}

// Child class inheriting an abstract class
class HomeScreen extends StatefulWidget {
  @override
  void initState() {
    super.initState();
    print("HomeScreen Initialized!");
  }

  @override
  int build(bool context) {
    print("Building HomeScreen...");
    return 0;
  }
}

void main() {
  HomeScreen home = HomeScreen();
  home.initState();
  home.build(true);
}
```
📌 **Key Points:**  
✅ `StatefulWidget` is an **abstract class** in Flutter.  
✅ `initState()` is a **concrete method**, while `build()` is an **abstract method** that must be implemented.  

---

## **4. Summary**  
| Feature           | Data Abstraction | Abstract Class |
|------------------|----------------|---------------|
| Purpose         | Hide data details | Define base class for inheritance |
| Usage           | Secure private attributes | Create abstract & concrete methods |
| Object Creation | ✅ (Yes) | ❌ (No) |
| Inheritance     | ✅ (Optional) | ✅ (Required) |
| Example         | Getter & Setter | `abstract class A {}` |

---

This README-style explanation simplifies **data abstraction and abstract classes in Dart** for better understanding. Let me know if you need more refinements! 🚀
