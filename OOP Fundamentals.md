# Day 1 – OOP Fundamentals (Interview Focus)



⏰ **Study Time: 5–6 Hours**

Goal:

* Understand OOP basics deeply.
* Be able to answer basic OOP interview questions confidently.

---

# Topic 1: What is OOP?

### Definition

Object-Oriented Programming (OOP) is a programming paradigm that organizes software using **objects and classes**.

### Real-World Example

Think of a car.

**Properties (Data):**

* Color
* Model
* Speed

**Functions (Behavior):**

* Start()
* Stop()
* Accelerate()

The car is an **object**.

---

### Interview Answer

> OOP is a programming paradigm that uses classes and objects to organize code. It improves code reusability, maintainability, and scalability through concepts like encapsulation, abstraction, inheritance, and polymorphism.

---

# Topic 2: Class and Object

## Class

A class is a blueprint or template.

### Example

```cpp
class Student
{
public:
    string name;
    int age;
};
```

Student is only a blueprint.

---

## Object

An object is an instance of a class.

```cpp
Student s1;
```

Now memory is allocated.

---

### Real-World Example

| Class   | Object      |
| ------- | ----------- |
| Car     | BMW         |
| Student | Chethan     |
| Mobile  | Samsung S24 |

---

### Interview Question

### Class vs Object

| Class               | Object           |
| ------------------- | ---------------- |
| Blueprint           | Real instance    |
| No memory allocated | Memory allocated |
| Logical entity      | Physical entity  |

---

# Topic 3: Access Specifiers

Controls access to data.

## Public

Accessible everywhere.

```cpp
public:
    int age;
```

---

## Private

Accessible only inside class.

```cpp
private:
    int salary;
```

---

## Protected

Accessible inside class and derived classes.

```cpp
protected:
    int marks;
```

---

### Difference Table

| Access    | Same Class | Derived Class | Outside Class |
| --------- | ---------- | ------------- | ------------- |
| Public    | Yes        | Yes           | Yes           |
| Protected | Yes        | Yes           | No            |
| Private   | Yes        | No            | No            |

---

Here are three clear C++ code examples that demonstrate **public**, **private**, and **protected** access specifiers in action:

---

### 🔹 Example 1: Public Access
```cpp
#include <iostream>
using namespace std;

class Student {
public:
    int age;  // Public: accessible everywhere
};

int main() {
    Student s;
    s.age = 20;  // Accessible directly
    cout << "Age: " << s.age << endl;
    return 0;
}
```
✅ Output: `Age: 20`  
👉 Public members can be accessed directly outside the class.

---

### 🔹 Example 2: Private Access
```cpp
#include <iostream>
using namespace std;

class Employee {
private:
    int salary;  // Private: accessible only inside class

public:
    void setSalary(int s) {
        salary = s;  // Allowed inside class
    }
    int getSalary() {
        return salary;  // Allowed inside class
    }
};

int main() {
    Employee e;
    // e.salary = 5000; ❌ Error: salary is private
    e.setSalary(5000);  // ✅ Use setter
    cout << "Salary: " << e.getSalary() << endl;
    return 0;
}
```
✅ Output: `Salary: 5000`  
👉 Private members require **getter/setter functions** to access them.

---

### 🔹 Example 3: Protected Access
```cpp
#include <iostream>
using namespace std;

class Person {
protected:
    int marks;  // Protected: accessible in derived class
};

class Student : public Person {
public:
    void setMarks(int m) {
        marks = m;  // ✅ Accessible in derived class
    }
    void showMarks() {
        cout << "Marks: " << marks << endl;
    }
};

int main() {
    Student s;
    // s.marks = 90; ❌ Error: marks is protected
    s.setMarks(90);  // ✅ Access via derived class method
    s.showMarks();
    return 0;
}
```
✅ Output: `Marks: 90`  
👉 Protected members are **not accessible outside the class**, but **can be used in derived classes**.

---

✨ These three examples neatly illustrate the difference:
- **Public** → accessible everywhere.  
- **Private** → only inside the class.  
- **Protected** → inside class + derived classes.  

Would you like me to also create a **combined example** showing all three specifiers in a single class for easier comparison?

# Topic 4: Constructor

### Definition

A special function called automatically when an object is created.

### Example

```cpp
class Student
{
public:
    Student()
    {
        cout<<"Constructor Called";
    }
};
```

---

### Output

```text
Constructor Called
```

---

### Why Constructor?

Used to initialize objects.

---

### Real-World Example

When a new bank account is opened, initial details are automatically assigned.

---

Got it — let’s build **full notes on Constructors in C++** so you have everything in one place for study and revision.  

---

# 📘 Full Notes: Constructors in C++

## 🔹 Definition
- A **constructor** is a special member function of a class.  
- Same name as the class.  
- No return type (not even `void`).  
- Called **automatically** when an object is created.  
- Used to **initialize data members**.

---

## 🔹 Characteristics
- Runs **only once** when the object is created.  
- Cannot be called explicitly like normal functions.  
- Can be **overloaded** (multiple constructors in one class).  
- If no constructor is defined, compiler provides a **default constructor**.  
- Can be **public** or **protected**, but usually public.  
- Cannot be inherited, but derived classes can call base class constructors.  

---

## 🔹 Why Constructors Are Needed
- Prevents **garbage values** in objects.  
- Ensures every object starts in a **valid state**.  
- Saves time: initialization happens **immediately** at object creation.  
- Makes code **cleaner and safer**.  

👉 Example: A `BankAccount` should always start with an account number and balance. Constructors guarantee this.

---

## 🔹 Types of Constructors

### 1. Default Constructor
- No parameters.  
- Provides default values.  

```cpp
class Student {
public:
    int age;
    Student() {  // Default constructor
        age = 18;
    }
};
```

👉 `Student s;` → age = 18.

---

### 2. Parameterized Constructor
- Takes arguments.  
- Allows setting values while creating objects.  

```cpp
class Employee {
private:
    int salary;
public:
    Employee(int s) {  // Parameterized constructor
        salary = s;
    }
};
```

👉 `Employee e(5000);` → salary = 5000.

---

### 3. Copy Constructor
- Creates a new object by copying another.  

```cpp
class Person {
public:
    int marks;
    Person(int m) { marks = m; }
    Person(const Person &p) {  // Copy constructor
        marks = p.marks;
    }
};
```

👉 `Person p2 = p1;` → copies marks from `p1`.

---

## 🔹 When Copy Constructor is Called
- Initializing one object with another: `Person p2 = p1;`  
- Passing object by value to a function.  
- Returning object from a function.  

---

## 🔹 Constructor Overloading
- Multiple constructors with different parameter lists.  

```cpp
class Box {
public:
    int length;
    Box() { length = 10; }          // Default
    Box(int l) { length = l; }      // Parameterized
};
```

👉 `Box b1;` → length = 10  
👉 `Box b2(20);` → length = 20  

---

## 🔹 Constructor vs Normal Function
| Feature              | Constructor | Normal Function |
|----------------------|-------------|-----------------|
| Name                 | Same as class | Any valid name |
| Return type          | None        | Has return type |
| Called automatically | Yes         | No (must be called) |
| Purpose              | Initialize object | Perform operations |

---

## 🔹 Special Notes
- **Destructor** is the opposite of constructor → cleans up when object is destroyed.  
- **Initialization lists** can be used in constructors for efficiency:  
```cpp
class Student {
    int age;
public:
    Student(int a) : age(a) {}  // Initialization list
};
```
- Constructors can be **explicit** to avoid implicit conversions.  

---

## ✅ Summary
- **Constructor** → special function to initialize objects.  
- **Default** → sets default values.  
- **Parameterized** → allows custom values.  
- **Copy** → duplicates an existing object.  
- **Overloading** → multiple constructors in one class.  
- Ensures objects are always created in a **valid state**.  

---

Do you want me to also add **full notes on Destructors** right after this, so you’ll have the complete “Constructor + Destructor” pair for your study material?
---

# 📘 Full Notes: Constructors in C++

## 🔹 What is a Constructor?
- Special member function of a class.  
- Same name as the class.  
- No return type (not even `void`).  
- Called **automatically** when an object is created.  
- Used to **initialize data members**.

---

## 🔹 Why Constructors Are Needed
- Prevents **garbage values** in objects.  
- Ensures every object starts in a **valid state**.  
- Saves time: initialization happens **immediately** at object creation.  
- Makes code **cleaner and safer**.  

---

## 🔹 Types of Constructors with Code Examples

### 1. Default Constructor
```cpp
#include <iostream>
using namespace std;

class Student {
public:
    int age;

    // Default constructor
    Student() {
        age = 18;  // Default value
        cout << "Default constructor called!" << endl;
    }
};

int main() {
    Student s;  // Constructor runs automatically
    cout << "Age: " << s.age << endl;
    return 0;
}
```

👉 Output:
```
Default constructor called!
Age: 18
```

---

### 2. Parameterized Constructor
```cpp
#include <iostream>
using namespace std;

class Employee {
private:
    int salary;

public:
    // Parameterized constructor
    Employee(int s) {
        salary = s;
        cout << "Parameterized constructor called!" << endl;
    }

    void showSalary() {
        cout << "Salary: " << salary << endl;
    }
};

int main() {
    Employee e(5000);  // Pass value while creating object
    e.showSalary();
    return 0;
}
```

👉 Output:
```
Parameterized constructor called!
Salary: 5000
```

---

### 3. Copy Constructor
```cpp
#include <iostream>
using namespace std;

class Person {
public:
    int marks;

    // Parameterized constructor
    Person(int m) {
        marks = m;
    }

    // Copy constructor
    Person(const Person &p) {
        marks = p.marks;
        cout << "Copy constructor called!" << endl;
    }

    void showMarks() {
        cout << "Marks: " << marks << endl;
    }
};

int main() {
    Person p1(90);     // Normal constructor
    Person p2 = p1;    // Copy constructor runs
    p2.showMarks();
    return 0;
}
```

👉 Output:
```
Copy constructor called!
Marks: 90
```

---

## 🔹 Constructor Overloading
```cpp
#include <iostream>
using namespace std;

class Box {
public:
    int length;

    // Default constructor
    Box() {
        length = 10;
    }

    // Parameterized constructor
    Box(int l) {
        length = l;
    }
};

int main() {
    Box b1;       // Default constructor
    Box b2(20);   // Parameterized constructor

    cout << "Box1 length: " << b1.length << endl;
    cout << "Box2 length: " << b2.length << endl;
    return 0;
}
```

👉 Output:
```
Box1 length: 10
Box2 length: 20
```

---

## 🔹 Key Points
- Constructor runs **automatically** at object creation.  
- Can be **overloaded** (multiple constructors).  
- Copy constructor is used when:
  - Initializing one object with another.  
  - Passing object by value.  
  - Returning object from a function.  
- If no constructor is defined, compiler provides a **default one**.  

---

## 🔹 Constructor vs Normal Function
| Feature              | Constructor | Normal Function |
|----------------------|-------------|-----------------|
| Name                 | Same as class | Any valid name |
| Return type          | None        | Has return type |
| Called automatically | Yes         | No (must be called) |
| Purpose              | Initialize object | Perform operations |

---

✅ **Summary:**  
- **Default constructor** → sets default values.  
- **Parameterized constructor** → allows custom values.  
- **Copy constructor** → duplicates an existing object.  
- **Overloading** → multiple constructors in one class.  
- Ensures objects are always created in a **valid state**.  

---
# Topic 5: Destructor

Alright chethan, here are **complete notes on Destructors in C++** with full code examples so you can study them alongside constructors.

---

# 📘 Full Notes: Destructors in C++

## 🔹 What is a Destructor?
- A **destructor** is a special member function of a class.  
- Same name as the class but preceded by a **tilde (~)**.  
- Called **automatically** when an object goes out of scope or is deleted.  
- Used to **release resources** (like memory, files, or connections).  
- Has **no return type** and **no parameters**.  
- Only **one destructor per class** (cannot be overloaded).

---

## 🔹 Why Destructors Are Needed
- To clean up when an object is destroyed.  
- Prevents **memory leaks** (unused memory not freed).  
- Ensures files or resources are properly closed.  
- Important in programs that use **dynamic memory allocation** (`new` / `delete`).  

---

## 🔹 Syntax
```cpp
class ClassName {
public:
    ~ClassName() {
        // cleanup code
    }
};
```

---

## 🔹 Example 1: Basic Destructor
```cpp
#include <iostream>
using namespace std;

class Student {
public:
    Student() {
        cout << "Constructor called!" << endl;
    }

    ~Student() {
        cout << "Destructor called!" << endl;
    }
};

int main() {
    Student s;  // Constructor runs here
    // Destructor runs automatically at end of scope
    return 0;
}
```

👉 Output:
```
Constructor called!
Destructor called!
```

---

## 🔹 Example 2: Destructor with Dynamic Memory
```cpp
#include <iostream>
using namespace std;

class Array {
private:
    int* data;
    int size;

public:
    Array(int s) {
        size = s;
        data = new int[size];  // allocate memory
        cout << "Constructor: Memory allocated!" << endl;
    }

    ~Array() {
        delete[] data;  // free memory
        cout << "Destructor: Memory freed!" << endl;
    }
};

int main() {
    Array arr(5);  // Constructor allocates memory
    // Destructor frees memory automatically at end
    return 0;
}
```

👉 Output:
```
Constructor: Memory allocated!
Destructor: Memory freed!
```

---

## 🔹 Example 3: Destructor with File Handling
```cpp
#include <iostream>
#include <fstream>
using namespace std;

class Logger {
private:
    ofstream file;

public:
    Logger() {
        file.open("log.txt");
        cout << "Constructor: File opened!" << endl;
    }

    ~Logger() {
        file.close();
        cout << "Destructor: File closed!" << endl;
    }
};

int main() {
    Logger log;  // File opened
    // Destructor closes file automatically
    return 0;
}
```

👉 Output:
```
Constructor: File opened!
Destructor: File closed!
```

---

## 🔹 Key Points
- Destructor is **automatic** → no need to call manually.  
- Only **one destructor per class**.  
- Cannot be overloaded.  
- Used for **cleanup tasks** (memory, files, connections).  
- Runs in **reverse order of construction** (last object created is destroyed first).  

---

## 🔹 Constructor vs Destructor

| Feature              | Constructor | Destructor |
|----------------------|-------------|------------|
| Name                 | Same as class | ~ClassName |
| Purpose              | Initialize object | Clean up resources |
| Called automatically | At object creation | At object destruction |
| Parameters           | Allowed (can overload) | Not allowed (only one) |
| Overloading          | Possible | Not possible |

---

✅ **Summary:**  
- **Constructor** → initializes objects.  
- **Destructor** → cleans up when objects are destroyed.  
- Together, they ensure safe **creation and destruction** of objects.  

---
Perfect, chethan! Let’s put **constructors and destructors together** in one full program so you can see how they work side by side.

---

# 📘 Combined Notes: Constructor + Destructor in C++

## 🔹 Key Idea
- **Constructor** → runs when object is created (initializes data).  
- **Destructor** → runs when object is destroyed (cleans up resources).  
- They always come in **pairs**: constructor at the start, destructor at the end.  

---

## 🔹 Full Code Example
```cpp
#include <iostream>
using namespace std;

class Student {
private:
    int age;

public:
    // Constructor
    Student(int a) {
        age = a;
        cout << "Constructor: Object created with age = " << age << endl;
    }

    // Destructor
    ~Student() {
        cout << "Destructor: Object destroyed for age = " << age << endl;
    }

    void showAge() {
        cout << "Age is: " << age << endl;
    }
};

int main() {
    cout << "Program started..." << endl;

    Student s1(20);   // Constructor runs here
    s1.showAge();

    {
        Student s2(25);  // Constructor runs
        s2.showAge();
        // Destructor runs automatically when s2 goes out of scope (end of block)
    }

    cout << "Back in main, before ending..." << endl;

    // Destructor for s1 runs automatically at end of main
    return 0;
}
```

---

## 🔹 Example Output
```
Program started...
Constructor: Object created with age = 20
Age is: 20
Constructor: Object created with age = 25
Age is: 25
Destructor: Object destroyed for age = 25
Back in main, before ending...
Destructor: Object destroyed for age = 20
```

---

## 🔹 Key Points
- Constructor runs **when object is created**.  
- Destructor runs **when object goes out of scope** or program ends.  
- If you create objects inside a block `{ ... }`, their destructor runs as soon as the block ends.  
- Useful for managing **resources** (memory, files, connections).  

---

✅ **Summary:**  
- Constructor → sets up the object.  
- Destructor → cleans up the object.  
- Together, they ensure safe **lifecycle management** of objects.  

---


---

# Topic 6: Static Keyword
Alright chethan, let’s dive into **Static Keyword in C++** with full notes and examples so you get the complete picture.

---

# 📘 Full Notes: `static` Keyword in C++

## 🔹 What is `static`?
The `static` keyword in C++ changes the **lifetime** and **scope** of variables, functions, and class members.  
It means:  
- The variable/function **retains its value** between calls.  
- Memory is allocated **only once** for the lifetime of the program.  

---

## 🔹 Uses of `static`

### 1. Static Local Variables
- Declared inside a function.  
- Value is **retained** between function calls.  
- Initialized only once.

```cpp
#include <iostream>
using namespace std;

void counter() {
    static int count = 0;  // static local variable
    count++;
    cout << "Count: " << count << endl;
}

int main() {
    counter();  // Count: 1
    counter();  // Count: 2
    counter();  // Count: 3
    return 0;
}
```

👉 Without `static`, `count` would reset to 0 every time.

---

### 2. Static Global Variables
- Declared outside functions.  
- Scope is limited to the file (not accessible from other files).  

```cpp
#include <iostream>
using namespace std;

static int globalVar = 10;  // static global variable

int main() {
    cout << "GlobalVar: " << globalVar << endl;
    return 0;
}
```

👉 Normal global variables can be accessed across files, but `static` restricts them to the current file.

---

### 3. Static Data Members in Class
- Shared by **all objects** of the class.  
- Only one copy exists, no matter how many objects are created.  

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    static int count;  // static data member

    Student() {
        count++;
    }
};

int Student::count = 0;  // initialize static member

int main() {
    Student s1, s2, s3;
    cout << "Number of students: " << Student::count << endl;
    return 0;
}
```

👉 Output:
```
Number of students: 3
```

---

### 4. Static Member Functions
- Belong to the class, not to any object.  
- Can access only **static data members**.  
- Called using `ClassName::functionName()`.

```cpp
#include <iostream>
using namespace std;

class Employee {
private:
    static int salary;

public:
    static void setSalary(int s) {
        salary = s;
    }

    static void showSalary() {
        cout << "Salary: " << salary << endl;
    }
};

int Employee::salary = 0;  // initialize static member

int main() {
    Employee::setSalary(5000);
    Employee::showSalary();
    return 0;
}
```

👉 Output:
```
Salary: 5000
```

---

## 🔹 Key Points
- **Static local variable** → retains value between function calls.  
- **Static global variable** → scope limited to file.  
- **Static data member** → shared among all objects.  
- **Static member function** → can access only static members.  

---

✅ **Summary:**  
The `static` keyword is used to **control lifetime and scope**. It’s powerful for:  
- Remembering values between calls.  
- Restricting global scope.  
- Sharing data among all objects of a class.  
- Creating class-level functions.  

---
---

# Most Asked Day-1 Interview Questions

### Easy

1. What is OOP?
2. Why do we use OOP?
3. What is a class?
4. What is an object?
5. Difference between class and object?
6. What is a constructor?
7. What is a destructor?
8. Why are constructors used?
9. What is a static variable?
10. What are access specifiers?

---

### Medium

11. Can a class exist without an object?
12. Can an object exist without a class?
13. Can constructors be overloaded?
14. Can constructors be private?
15. What happens if no constructor is defined?

---

### Tricky

16. Is constructor inherited?
17. Is destructor inherited?
18. Can constructor be virtual?
19. Can constructor return a value?
20. Can destructor be overloaded?

---

# Day 1 Revision Notes (Must Memorize)

### Definitions

✅ OOP

✅ Class

✅ Object

✅ Constructor

✅ Destructor

✅ Static Variable

✅ Public / Private / Protected

---

# End of Day 1 Target

By the end of today, you should be able to answer without notes:

1. What is OOP?
2. Class vs Object.
3. Constructor vs Destructor.
4. Public vs Private vs Protected.
5. Why use OOP?
6. Real-world example of Class and Object.


# Day 1 OOP Interview Questions & Answers

---

# Easy Questions

## 1. What is OOP?

### Answer

OOP (Object-Oriented Programming) is a programming paradigm that uses **classes and objects** to organize code and data together.

### Example

A Car object contains:

* Data → color, speed
* Functions → start(), stop()

### Benefits

* Reusability
* Security
* Easy maintenance
* Scalability

---

## 2. Why do we use OOP?

### Answer

We use OOP to make programs:

* Easier to maintain
* Reusable
* Secure
* Modular

### Interview Answer

> OOP helps organize code into objects, making software easier to develop, maintain, and reuse.

---

## 3. What is a Class?

### Answer

A class is a blueprint or template used to create objects.

### Example

```cpp
class Student
{
public:
    string name;
    int age;
};
```

Student is a class.

---

## 4. What is an Object?

### Answer

An object is an instance of a class.

### Example

```cpp
Student s1;
```

s1 is an object.

---

## 5. Difference between Class and Object?

| Class                  | Object             |
| ---------------------- | ------------------ |
| Blueprint              | Instance           |
| Logical entity         | Physical entity    |
| No memory allocated    | Memory allocated   |
| Used to create objects | Created from class |

### Example

* Class → Car
* Object → BMW

---

## 6. What is a Constructor?

### Answer

A constructor is a special member function that is automatically called when an object is created.

### Example

```cpp
class Test
{
public:
    Test()
    {
        cout<<"Constructor";
    }
};
```

### Purpose

Initialize object data.

---

## 7. What is a Destructor?

### Answer

A destructor is a special member function that is automatically called when an object is destroyed.

### Example

```cpp
class Test
{
public:
    ~Test()
    {
        cout<<"Destructor";
    }
};
```

### Purpose

Release memory and resources.

---

## 8. Why are Constructors Used?

### Answer

Constructors are used to initialize objects automatically.

### Example

```cpp
Student s1;
```

As soon as s1 is created, constructor runs automatically.

---

## 9. What is a Static Variable?

### Answer

A static variable is shared among all objects of a class.

### Example

```cpp
class Student
{
public:
    static int count;
};
```

Only one copy exists.

### Real Example

College name is same for all students.

---

## 10. What are Access Specifiers?

### Answer

Access specifiers control access to class members.

### Types

| Access Specifier | Access                       |
| ---------------- | ---------------------------- |
| Public           | Anywhere                     |
| Private          | Within class only            |
| Protected        | Within class + derived class |

---

# Medium Questions

---

## 11. Can a Class Exist Without an Object?

### Answer

Yes.

A class can exist without creating any object.

### Example

```cpp
class Student
{
};
```

No object created, but class exists.

---

## 12. Can an Object Exist Without a Class?

### Answer

No.

Every object must be created from a class.

### Interview Answer

> An object is an instance of a class, so it cannot exist without a class.

---

## 13. Can Constructors Be Overloaded?

### Answer

Yes.

A class can have multiple constructors with different parameters.

### Example

```cpp
class Student
{
public:
    Student()
    {
    }

    Student(int age)
    {
    }
};
```

This is constructor overloading.

---

## 14. Can Constructors Be Private?

### Answer

Yes.

Private constructors prevent object creation outside the class.

### Example

```cpp
class Test
{
private:
    Test()
    {
    }
};
```

Often used in Singleton Design Pattern.

---

## 15. What Happens If No Constructor Is Defined?

### Answer

The compiler automatically creates a default constructor.

### Example

```cpp
class Student
{
};
```

Compiler internally creates:

```cpp
Student()
{
}
```

---

# Tricky Questions

---

## 16. Is Constructor Inherited?

### Answer

No.

Constructors are not inherited.

### Example

```cpp
class Parent
{
public:
    Parent()
    {
    }
};

class Child : public Parent
{
};
```

Child does not inherit Parent constructor.

Parent constructor is called automatically during object creation.

---

## 17. Is Destructor Inherited?

### Answer

No.

Destructors are not inherited.

Each class has its own destructor.

### Interview Answer

> Destructors are not inherited, but base class destructors are automatically called when derived class objects are destroyed.

---

## 18. Can Constructor Be Virtual?

### Answer

No.

Constructors cannot be virtual.

### Reason

Object must exist before virtual mechanism works.

### Interview Answer

> Constructors cannot be virtual because virtual functions require a fully created object.

---

## 19. Can Constructor Return a Value?

### Answer

No.

Constructors do not have any return type.

### Wrong

```cpp
int Student()
{
}
```

### Correct

```cpp
Student()
{
}
```

---

## 20. Can Destructor Be Overloaded?

### Answer

No.

A class can have only one destructor.

### Wrong

```cpp
~Student()
{
}

~Student(int x)
{
}
```

Compiler error.

---

# Frequently Asked in Interviews

### Top 5

1. What is OOP?
2. Class vs Object?
3. Constructor vs Destructor?
4. Can constructors be overloaded?
5. Can constructors be virtual?

These five questions appear very often in fresher interviews and viva exams.


If you complete Day 1 properly, Day 2 (OOP Pillars: Encapsulation, Abstraction, Inheritance, Polymorphism) becomes much easier and covers the most frequently asked OOP interview questions.
