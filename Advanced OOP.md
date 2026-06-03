# Day 3 – Advanced OOP (Very Important for Interviews)

Today focuses on topics that interviewers often ask after the basic OOP questions.

---

# Topics to Learn

## 1. Function Overloading

## 2. Operator Overloading

## 3. Function Overriding

## 4. Virtual Functions

## 5. Dynamic Binding (Late Binding)

## 6. Abstract Classes

## 7. Pure Virtual Functions

## 8. Interface

## 9. Friend Function

## 10. This Pointer

---

# 1. Function Overloading

Alright chethan, let’s dive into **Function Overloading** in C++ — step by step with examples so you can master it.

---

## 🔹 What is Function Overloading?
- Function overloading means having **multiple functions with the same name** but **different parameter lists**.  
- The compiler decides which function to call based on the **number** or **type** of arguments.  
- It’s a form of **compile-time polymorphism**.

👉 Example in real life:  
Think of the word **“print”** — you can print an integer, a string, or a float. Same name, different behavior.

---

## 🔹 Rules of Function Overloading
1. Functions must differ in **parameter type** or **number of parameters**.  
2. Return type alone **cannot** distinguish overloaded functions.  
3. Overloading improves **readability** and **reusability**.

---

## 🔹 Example 1: Basic Function Overloading
```cpp
#include <iostream>
using namespace std;

class Print {
public:
    void show(int x) {
        cout << "Integer: " << x << endl;
    }

    void show(double y) {
        cout << "Double: " << y << endl;
    }

    void show(string z) {
        cout << "String: " << z << endl;
    }
};

int main() {
    Print p;
    p.show(10);        // calls show(int)
    p.show(3.14);      // calls show(double)
    p.show("Hello");   // calls show(string)
    return 0;
}
```

👉 Output:
```
Integer: 10
Double: 3.14
String: Hello
```

---

## 🔹 Example 2: Different Number of Parameters
```cpp
#include <iostream>
using namespace std;

class Math {
public:
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
};

int main() {
    Math m;
    cout << "Sum of 2 numbers: " << m.add(5, 10) << endl;
    cout << "Sum of 3 numbers: " << m.add(5, 10, 15) << endl;
    return 0;
}
```

👉 Output:
```
Sum of 2 numbers: 15
Sum of 3 numbers: 30
```

---

## 🔹 Example 3: Operator Overloading (special case)
```cpp
#include <iostream>
using namespace std;

class Complex {
public:
    int real, imag;

    Complex(int r=0, int i=0) {
        real = r;
        imag = i;
    }

    // Overload + operator
    Complex operator + (const Complex& c) {
        return Complex(real + c.real, imag + c.imag);
    }

    void display() {
        cout << real << " + " << imag << "i" << endl;
    }
};

int main() {
    Complex c1(3, 4), c2(1, 2);
    Complex c3 = c1 + c2;  // uses overloaded +
    c3.display();
    return 0;
}
```

👉 Output:
```
4 + 6i
```

---

## 🔹 Key Points
- Function overloading = same name, different parameters.  
- Improves readability and reduces confusion.  
- Return type alone cannot distinguish overloaded functions.  
- Operator overloading is a special case of function overloading.  

---

✅ **Summary:**  
Function overloading is a way to make functions more flexible.  
- Same name, different parameter lists.  
- Decided at **compile time**.  
- Helps write clean, reusable code.  

---


> Function overloading allows multiple functions with the same name but different parameter lists.

---

# 2. Operator Overloading

Alright chethan, let’s explore **Operator Overloading** in C++ — this is a special case of polymorphism where we redefine how operators work for user-defined types.

---

## 🔹 What is Operator Overloading?
- Operator overloading allows you to **give new meaning to operators** (`+`, `-`, `*`, `==`, etc.) for your own classes.  
- It makes objects behave more like built-in types.  
- Achieved by defining a special function using the keyword `operator`.

👉 Example in real life:  
Think of `+` → normally adds numbers. With operator overloading, you can make `+` add two complex numbers or concatenate strings.

---

## 🔹 Syntax
```cpp
returnType operator symbol (parameters) {
    // custom implementation
}
```

---

## 🔹 Example 1: Overloading `+` for Complex Numbers
```cpp
#include <iostream>
using namespace std;

class Complex {
private:
    int real, imag;

public:
    Complex(int r=0, int i=0) {
        real = r;
        imag = i;
    }

    // Overload + operator
    Complex operator + (const Complex& c) {
        return Complex(real + c.real, imag + c.imag);
    }

    void display() {
        cout << real << " + " << imag << "i" << endl;
    }
};

int main() {
    Complex c1(3, 4), c2(1, 2);
    Complex c3 = c1 + c2;  // uses overloaded +
    c3.display();
    return 0;
}
```

👉 Output:
```
4 + 6i
```

---

## 🔹 Example 2: Overloading `==` for Comparison
```cpp
#include <iostream>
using namespace std;

class Student {
private:
    int id;

public:
    Student(int i) { id = i; }

    // Overload == operator
    bool operator == (const Student& s) {
        return id == s.id;
    }
};

int main() {
    Student s1(101), s2(101), s3(102);

    if(s1 == s2)
        cout << "s1 and s2 are equal" << endl;
    else
        cout << "s1 and s2 are not equal" << endl;

    if(s1 == s3)
        cout << "s1 and s3 are equal" << endl;
    else
        cout << "s1 and s3 are not equal" << endl;

    return 0;
}
```

👉 Output:
```
s1 and s2 are equal
s1 and s3 are not equal
```

---

## 🔹 Example 3: Overloading `<<` for Output
```cpp
#include <iostream>
using namespace std;

class Point {
private:
    int x, y;

public:
    Point(int a, int b) { x = a; y = b; }

    // Overload << operator
    friend ostream& operator << (ostream& out, const Point& p) {
        out << "(" << p.x << ", " << p.y << ")";
        return out;
    }
};

int main() {
    Point p1(10, 20);
    cout << "Point is: " << p1 << endl;  // uses overloaded <<
    return 0;
}
```

👉 Output:
```
Point is: (10, 20)
```

---

## 🔹 Key Points
- Operator overloading makes objects behave like built-in types.  
- Commonly overloaded operators: `+`, `-`, `*`, `==`, `<<`, `>>`.  
- Cannot overload: `::`, `.?`, `sizeof`, `typeid`.  
- Improves readability and usability of custom classes.  

---

✅ **Summary:**  
Operator overloading = redefining operators for user-defined types.  
- Example: `+` for complex numbers, `==` for comparison, `<<` for output.  
- Makes code intuitive and object-oriented.  

---

### Interview Answer

> Operator overloading allows operators to work with user-defined data types.

---

# 3. Function Overriding

Alright chethan, let’s break down **Function Overriding** in C++ step by step so you can really see how it works.

---

## 🔹 What is Function Overriding?
- Function overriding happens when a **derived class** provides its own definition of a function that already exists in the **base class**.  
- The function must have the **same name, parameters, and return type**.  
- It’s a form of **runtime polymorphism** (decided at run time).  
- The base class function should be marked as **`virtual`** to allow overriding.

👉 Think of it like this:  
A base class defines a general behavior, but the derived class can **customize** it.

---

## 🔹 Example Code
```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void sound() {   // virtual function
        cout << "Animal makes a sound" << endl;
    }
};

class Dog : public Animal {
public:
    void sound() override {  // overriding
        cout << "Dog barks" << endl;
    }
};

class Cat : public Animal {
public:
    void sound() override {
        cout << "Cat meows" << endl;
    }
};

int main() {
    Animal* a1 = new Dog();
    Animal* a2 = new Cat();

    a1->sound();   // Dog’s version
    a2->sound();   // Cat’s version

    delete a1;
    delete a2;
    return 0;
}
```

👉 Output:
```
Dog barks
Cat meows
```

---

## 🔹 Key Rules
1. Function name, parameters, and return type must match.  
2. Base class function should be marked `virtual`.  
3. Derived class function can use `override` (optional but recommended).  
4. Overriding works only with **inheritance**.  
5. Decided at **runtime** using base class pointers/references.  

---

## 🔹 Difference: Overloading vs Overriding
- **Overloading** → same name, different parameters, compile-time.  
- **Overriding** → same name, same parameters, runtime, requires inheritance.  

---

✅ **Summary:**  
Function overriding lets derived classes **customize behavior** of base class functions. It’s the backbone of **runtime polymorphism** in OOP.


# 4. Virtual Function

### Definition

A virtual function allows runtime polymorphism.

### Example

```cpp
class Animal
{
public:
    virtual void sound()
    {
        cout<<"Animal";
    }
};

class Dog : public Animal
{
public:
    void sound()
    {
        cout<<"Dog";
    }
};
```

---

### Why Virtual Function?

Without virtual:

```cpp
Animal *ptr = new Dog();
ptr->sound();
```

Output:

```text
Animal
```

With virtual:

```text
Dog
```

---

### Interview Answer

> A virtual function is a function declared with the virtual keyword that enables runtime polymorphism.

---

# 5. Dynamic Binding (Late Binding)

### Definition

Function call is resolved during runtime.

### Example

```cpp
Animal *ptr = new Dog();
ptr->sound();
```

Compiler decides at runtime which function to execute.

---

### Interview Answer

> Dynamic binding means the method call is resolved during program execution rather than during compilation.

---

# 6. Abstract Class

### Definition

A class containing at least one pure virtual function.

### Example

```cpp
class Shape
{
public:
    virtual void draw() = 0;
};
```

---

### Important

Cannot create objects of abstract class.

Wrong:

```cpp
Shape s;
```

---

### Interview Answer

> An abstract class is a class that contains at least one pure virtual function and cannot be instantiated.

---

# 7. Pure Virtual Function

### Definition

A virtual function assigned with = 0.

### Example

```cpp
virtual void draw() = 0;
```

---

### Purpose

Forces derived classes to implement the function.

---

### Interview Answer

> A pure virtual function has no implementation in the base class and must be implemented by derived classes.

---

# 8. Interface

### Definition

An interface is a class containing only pure virtual functions.

### Example

```cpp
class Vehicle
{
public:
    virtual void start() = 0;
    virtual void stop() = 0;
};
```

---

### Interview Answer

> An interface defines a contract that derived classes must implement.

---

# 9. Friend Function

### Definition

A function that can access private members of a class.

### Example

```cpp
class Test
{
private:
    int x = 10;

    friend void show(Test);
};
```

---

### Interview Answer

> A friend function is a non-member function that can access private and protected members of a class.

---

# 10. This Pointer

### Definition

A pointer that stores the address of the current object.

### Example

```cpp
class Student
{
public:
    int age;

    void setAge(int age)
    {
        this->age = age;
    }
};
```

---

### Interview Answer

> The this pointer refers to the current object of a class.

---

# Most Important Difference Tables

## Virtual Function vs Pure Virtual Function

| Virtual Function     | Pure Virtual Function  |
| -------------------- | ---------------------- |
| Has implementation   | No implementation      |
| Optional override    | Must override          |
| Runtime polymorphism | Creates abstract class |

---

## Abstract Class vs Interface

| Abstract Class             | Interface                 |
| -------------------------- | ------------------------- |
| May contain normal methods | Only pure virtual methods |
| Can have data members      | Usually no data members   |
| Partial abstraction        | Complete abstraction      |

---

## Static Binding vs Dynamic Binding

| Static Binding | Dynamic Binding   |
| -------------- | ----------------- |
| Compile Time   | Runtime           |
| Faster         | Slightly slower   |
| Overloading    | Virtual Functions |

---

# Frequently Asked Interview Questions

## Easy

1. What is function overloading?
2. What is function overriding?
3. What is a virtual function?
4. What is an abstract class?
5. What is a friend function?

---

## Medium

6. What is dynamic binding?
7. What is a pure virtual function?
8. What is an interface?
9. What is the this pointer?
10. Why are virtual functions used?

---

## Hard

11. Virtual Function vs Pure Virtual Function?
12. Abstract Class vs Interface?
13. Can we create an object of an abstract class?
14. Why can't constructors be virtual?
15. What happens if a virtual destructor is not used in inheritance?

---

# Day 3 End Goal

You should confidently answer:

✅ Overloading vs Overriding

✅ Virtual Function

✅ Dynamic Binding

✅ Abstract Class

✅ Interface

✅ Pure Virtual Function

These are the most common advanced OOP questions asked in technical interviews after the four pillars of OOP.


# Day 3 OOP Interview Questions & Answers

---

# Easy Questions

## 1. What is Function Overloading?

### Answer

Function overloading allows multiple functions with the same name but different parameters in the same class.

### Example

```cpp
add(int a, int b)
add(int a, int b, int c)
```

### Interview Answer

> Function overloading is a compile-time polymorphism where multiple functions have the same name but different parameter lists.

---

## 2. What is Function Overriding?

### Answer

Function overriding occurs when a derived class provides its own implementation of a function already defined in the base class.

### Example

```cpp
class Animal{
public:
    void sound(){
        cout<<"Animal";
    }
};

class Dog : public Animal{
public:
    void sound(){
        cout<<"Dog";
    }
};
```

### Interview Answer

> Function overriding allows a child class to redefine a method inherited from the parent class.

---

## 3. What is a Virtual Function?

### Answer

A virtual function is a function declared using the `virtual` keyword that enables runtime polymorphism.

### Example

```cpp
virtual void sound();
```

### Interview Answer

> A virtual function allows the correct overridden function to be called based on the actual object type at runtime.

---

## 4. What is an Abstract Class?

### Answer

A class containing at least one pure virtual function is called an abstract class.

### Example

```cpp
class Shape{
public:
    virtual void draw() = 0;
};
```

### Important

Objects of abstract classes cannot be created.

### Interview Answer

> An abstract class is a class that cannot be instantiated and is used as a base class for derived classes.

---

## 5. What is a Friend Function?

### Answer

A friend function is a non-member function that can access private and protected members of a class.

### Example

```cpp
class Test{
private:
    int x;

    friend void show(Test);
};
```

### Interview Answer

> A friend function is granted access to private and protected members even though it is not a member of the class.

---

# Medium Questions

---

## 6. What is Dynamic Binding?

### Answer

Dynamic binding means the function call is resolved during runtime rather than compile time.

### Example

```cpp
Animal *ptr = new Dog();
ptr->sound();
```

### Interview Answer

> Dynamic binding is the process of deciding which function to execute at runtime using virtual functions.

---

## 7. What is a Pure Virtual Function?

### Answer

A pure virtual function is a virtual function assigned with `= 0`.

### Example

```cpp
virtual void draw() = 0;
```

### Purpose

Forces derived classes to implement the function.

### Interview Answer

> A pure virtual function has no implementation in the base class and must be implemented by derived classes.

---

## 8. What is an Interface?

### Answer

An interface is a class containing only pure virtual functions.

### Example

```cpp
class Vehicle{
public:
    virtual void start() = 0;
    virtual void stop() = 0;
};
```

### Interview Answer

> An interface defines a contract that all derived classes must implement.

---

## 9. What is the This Pointer?

### Answer

`this` is a pointer that points to the current object.

### Example

```cpp
class Student{
public:
    int age;

    void setAge(int age){
        this->age = age;
    }
};
```

### Interview Answer

> The this pointer refers to the current object that invokes the member function.

---

## 10. Why are Virtual Functions Used?

### Answer

Virtual functions are used to achieve:

* Runtime polymorphism
* Dynamic binding
* Flexibility

### Interview Answer

> Virtual functions ensure that the correct overridden function is called at runtime based on the actual object type.

---

# Hard Questions

---

## 11. Virtual Function vs Pure Virtual Function?

| Virtual Function              | Pure Virtual Function |
| ----------------------------- | --------------------- |
| Has implementation            | No implementation     |
| Override optional             | Override mandatory    |
| Does not make class abstract  | Makes class abstract  |
| Used for runtime polymorphism | Used for abstraction  |

### Interview Answer

> A virtual function may have an implementation, while a pure virtual function has no implementation and must be overridden.

---

## 12. Abstract Class vs Interface?

| Abstract Class          | Interface                 |
| ----------------------- | ------------------------- |
| Can have normal methods | Only pure virtual methods |
| Can have data members   | Usually no data members   |
| Partial abstraction     | Complete abstraction      |
| More flexible           | Strict contract           |

### Interview Answer

> An abstract class provides partial abstraction, while an interface provides complete abstraction.

---

## 13. Can We Create an Object of an Abstract Class?

### Answer

No.

### Example

```cpp
Shape s;
```

This causes a compilation error.

### Reason

Abstract classes contain at least one pure virtual function.

### Interview Answer

> No, because abstract classes are incomplete and intended only to be inherited.

---

## 14. Why Can't Constructors Be Virtual?

### Answer

Virtual functions require a fully created object.

But constructors run while the object is still being created.

Therefore virtual dispatch is impossible.

### Interview Answer

> Constructors cannot be virtual because virtual functions need an existing object, but constructors execute before object creation is complete.

---

## 15. What Happens If a Virtual Destructor Is Not Used in Inheritance?

### Example

```cpp
Base *ptr = new Derived();
delete ptr;
```

If the base destructor is not virtual:

* Derived destructor may not execute.
* Resources allocated by the derived class may not be released.
* Memory leaks can occur.

### Correct

```cpp
class Base{
public:
    virtual ~Base(){}
};
```

### Interview Answer

> Without a virtual destructor, deleting a derived object through a base pointer may call only the base destructor, causing resource leaks and undefined behavior.

---

# Most Important Interview Questions from Day 3

### Q1. Overloading vs Overriding?

| Overloading           | Overriding         |
| --------------------- | ------------------ |
| Compile-time          | Runtime            |
| Same class            | Parent-child class |
| Different parameters  | Same parameters    |
| No inheritance needed | Inheritance needed |

---

### Q2. What is a Virtual Function?

> A virtual function enables runtime polymorphism by allowing function calls to be resolved at runtime.

---

### Q3. What is an Abstract Class?

> A class containing at least one pure virtual function that cannot be instantiated.

---

### Q4. Why Can't Constructors Be Virtual?

> Because virtual dispatch requires a fully constructed object, but constructors execute before object creation completes.

---

### Q5. Why Are Virtual Destructors Important?

> They ensure both base and derived destructors execute correctly when deleting objects through base class pointers.

These five questions are among the most frequently asked advanced OOP questions in technical interviews.
