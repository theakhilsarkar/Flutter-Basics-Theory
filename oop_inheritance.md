```markdown
# Inheritance in Dart

## Introduction

Inheritance is a fundamental concept in object-oriented programming (OOP) that allows a class (child class) to inherit properties and methods from another class (parent class). This promotes code reusability and establishes a hierarchical relationship between classes.

In Dart, inheritance is achieved using the `extends` keyword.

## Key Concepts

* **Parent Class (Superclass, Base Class):** The class whose properties and methods are inherited.
* **Child Class (Subclass, Derived Class):** The class that inherits from the parent class.
* **Inheritance:** The process of a child class acquiring the properties and methods of a parent class.
* **`extends` Keyword:** Used to specify that a class inherits from another class.
* **`super` Keyword:** Used to refer to the parent class within the child class.

## Benefits of Inheritance

* **Code Reusability:** Avoids redundant code by allowing child classes to reuse parent class members.
* **Extensibility:** Enables the creation of specialized classes based on existing classes.
* **Maintainability:** Easier to manage and modify code by organizing it into a hierarchy.
* **Polymorphism:** Allows objects of different classes to be treated as objects of a common parent class.

## Example

```dart
class Person {
  String? name, age, gender;

  void get() {
    print("Name : " + this.name!);
    print("Age : " + this.age!);
    print("Gender : " + this.gender!);
  }
}

class Employee extends Person {
  String? id, role, salary;

  Employee(name, age, gender, id, role, salary) {
    super.name = name;
    super.age = age;
    super.gender = gender;
    this.id = id;
    this.role = role;
    this.salary = salary;
  }

  void displayDetails() {
    super.get();
    print("Id : " + this.id!);
    print("Role : " + this.role!);
    print("Salary : " + this.salary!);
  }
}

void main() {
  Employee suraj = Employee("Suarj", "20", "Male", "10025", "Sr. Developer", "150000");
  suraj.displayDetails();
}
```

### Explanation

1.  **`Person` Class:**
    * Defines the basic attributes of a person (name, age, gender).
    * Contains a `get()` method to display these attributes.

2.  **`Employee` Class:**
    * Inherits from the `Person` class using `extends Person`.
    * Adds specific attributes for an employee (id, role, salary).
    * The constructor uses `super` to initialize the inherited attributes from the `Person` class.
    * The `displayDetails()` method calls the parent's `get()` method using `super.get()` and then displays the employee-specific details.

3.  **`main()` Function:**
    * Creates an `Employee` object `suraj`.
    * Calls the `displayDetails()` method to display the employee's information, including the inherited person information.

### Key Points

* Child classes can access and use the methods and attributes of their parent class.
* Parent classes cannot access the methods and attributes of their child classes (reverse inheritance is not possible).
* The `super` keyword is critical when you want to access parent class members from within a child class.
* Inheritance promotes code reuse and helps organize code into a logical hierarchy.
```
