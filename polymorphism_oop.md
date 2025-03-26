
# **Polymorphism in Object-Oriented Programming (OOP)**  

## **Introduction**  
Polymorphism is a fundamental concept of Object-Oriented Programming (OOP) that allows an object to perform in multiple ways.  

- A single entity can behave in different forms.  
- Different processes can work in a similar way, and sometimes the same process can behave differently.  

---

## **Types of Polymorphism**  

### **1. Compile-time Polymorphism**  
- Occurs **before the code runs** (during compilation).  
- Errors related to syntax occur at this stage.  
- Example: **Method Overloading**  
  - A single method can perform multiple tasks by changing parameters.  
  - Each function should perform a single process.  

### **2. Runtime Polymorphism**  
- Occurs **after the code is compiled and during execution**.  
- Bugs may occur at this stage.  
- Example: **Method Overriding**  
  - Requires **at least two classes** (inheritance).  
  - The parent class method is redefined in the child class with the same name but different functionality.  

---

## **Examples**  

### **1. Method Overloading (Compile-time Polymorphism)**  
In the below example, the `apiCall` method behaves in multiple ways based on the request type.  

```dart
class ApiHelper {
  // The apiCall method behaves in multiple ways
  void apiCall(String type) {
    if (type.toUpperCase() == 'GET') {
      print("GET API is called...!");
    } else if (type.toUpperCase() == 'POST') {
      print("POST API is called...!");
    }
  }
}

void main() {
  ApiHelper api = ApiHelper();
  api.apiCall('GET');  // Output: GET API is called...!
  api.apiCall('POST'); // Output: POST API is called...!
}
```

---

### **2. Method Overriding (Runtime Polymorphism)**  
Here, class `A` has a `get` method, which is overridden in class `B`.  

```dart
class A {
  void get(String name) {
    print("Class A method: $name");
  }
}

class B extends A {
  @override
  void get() {
    print("Class B method");
  }
}

void main() {
  A a1 = A();
  a1.get("Deep");  // Output: Class A method: Deep

  B b1 = B();
  b1.get();        // Output: Class B method
}
```

---

## **Key Takeaways**  
- **Method Overloading:** Single method performing multiple tasks (Compile-time).  
- **Method Overriding:** Child class modifying parent class method (Runtime).  
- **Polymorphism increases code flexibility and reusability.**  

This README simplifies the concept of **polymorphism in Dart** with **clear examples**. 🚀 Let me know if you want further refinements! 😊
