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

# Topic 5: Destructor

### Definition

Called automatically when object is destroyed.

### Example

```cpp
class Student
{
public:
    ~Student()
    {
        cout<<"Destructor Called";
    }
};
```

---

### Purpose

* Free memory
* Close files
* Release resources

---

# Constructor vs Destructor

| Constructor         | Destructor             |
| ------------------- | ---------------------- |
| Initializes object  | Destroys object        |
| Same name as class  | ~ClassName()           |
| Called at creation  | Called at deletion     |
| Can have parameters | Cannot have parameters |

---

# Topic 6: Static Keyword

## Static Variable

Shared by all objects.

```cpp
class Student
{
public:
    static int count;
};
```

---

### Example

Suppose 100 students exist.

Instead of storing college name 100 times,

store it once using static.

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
