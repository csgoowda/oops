Day 2 – OOP Pillars (Most Important Interview Topic)
⚠️ If an interviewer asks only one OOP question, it is often:
"Explain the 4 pillars of OOP with examples."
Master Day 2 thoroughly.
The 4 Pillars of OOP
Encapsulation
Abstraction
Inheritance
Polymorphism
1. Encapsulation
Definition
Encapsulation is the process of wrapping data and methods into a single unit (class) and restricting direct access to data.
Formula
Data + Methods = Encapsulation
Real-World Example
ATM Machine
You can:
Withdraw money
Deposit money
You cannot directly access:
Bank database
Internal processing
Data is hidden.
Example
class Bank
{
private:
    int balance;

public:
    void setBalance(int b)
    {
        balance = b;
    }

    int getBalance()
    {
        return balance;
    }
};
Advantages
Data security
Data hiding
Better control
Interview Answer
Encapsulation is wrapping data and methods into a single unit while restricting direct access using access specifiers.
2. Abstraction
Definition
Abstraction means showing only essential information and hiding implementation details.
Real-World Example
Car
You know:
Brake
Steering
Accelerator
You don't know:
Engine internals
Fuel injection process
Example
class Car
{
public:
    void start()
    {
        cout<<"Car Started";
    }
};
User only sees start().
Advantages
Reduces complexity
Improves security
Easy maintenance
Interview Answer
Abstraction hides implementation details and shows only essential features to the user.
Encapsulation vs Abstraction
Encapsulation	Abstraction
Hides data	Hides implementation
Uses access specifiers	Uses abstract classes/interfaces
Focus on security	Focus on simplicity


Easy Trick
Encapsulation → "How to protect?"
Abstraction → "How to simplify?"
3. Inheritance
Definition
Inheritance allows one class to acquire properties and methods of another class.
Real-World Example
Animal → Dog
Dog can:
Eat
Sleep
Because Dog inherits Animal.
Example
class Animal
{
public:
    void eat()
    {
        cout<<"Eating";
    }
};

class Dog : public Animal
{
};
Advantages
Code reusability
Reduced duplication
Easy maintenance
Types of Inheritance
Single Inheritance
A → B
Multilevel Inheritance
A → B → C
Multiple Inheritance
A
 \
  C
 /
B
Hierarchical Inheritance
      A
    /   \
   B     C
Hybrid Inheritance
Combination of multiple inheritance types.
Interview Answer
Inheritance allows a child class to acquire properties and methods from a parent class, promoting code reusability.
4. Polymorphism
Definition
Polymorphism means "many forms."
Same function behaves differently in different situations.
Types of Polymorphism
Compile-Time Polymorphism
Achieved through:
Function Overloading
Operator Overloading
Example
class Math
{
public:
    int add(int a,int b)
    {
        return a+b;
    }

    int add(int a,int b,int c)
    {
        return a+b+c;
    }
};
Same function name, different parameters.
Runtime Polymorphism
Achieved through:
Function Overriding
Virtual Functions
Example
class Animal
{
public:
    virtual void sound()
    {
        cout<<"Animal Sound";
    }
};

class Dog : public Animal
{
public:
    void sound()
    {
        cout<<"Bark";
    }
};
Advantages
Flexibility
Reusability
Extensibility
Interview Answer
Polymorphism allows the same interface or function to behave differently depending on the object.
Most Important Difference Tables
Overloading vs Overriding
Overloading	Overriding
Same class	Parent-child class
Different parameters	Same parameters
Compile-time	Runtime
No inheritance needed	Inheritance needed


Compile-Time vs Runtime Polymorphism
Compile-Time	Runtime
Faster	Slightly slower
Overloading	Overriding
Early binding	Late binding


Frequently Asked Interview Questions
Easy
What are the 4 pillars of OOP?
What is encapsulation?
What is abstraction?
What is inheritance?
What is polymorphism?
Medium
Encapsulation vs Abstraction?
Advantages of inheritance?
Types of inheritance?
What is function overloading?
What is function overriding?
Hard
Overloading vs Overriding?
Compile-time vs Runtime polymorphism?
Why is polymorphism useful?
Can we achieve runtime polymorphism without virtual functions?
Why is abstraction important?
End of Day 2 Target
You should be able to answer confidently:
✅ What are the 4 pillars of OOP?
✅ Encapsulation vs Abstraction
✅ Inheritance and its types
✅ Polymorphism and its types
✅ Overloading vs Overriding
These are among the most frequently asked OOP questions in placement interviews. Tomorrow (Day 3) focuses on Advanced OOP: Virtual Functions, Dynamic Binding, Abstract Classes, Interfaces, and frequently asked tricky OOP questions.


Day 2 OOP Interview Questions & Answers
Easy Questions
1. What are the 4 pillars of OOP?
Answer
The four pillars of OOP are:
Encapsulation
Abstraction
Inheritance
Polymorphism
These concepts help make code reusable, secure, and maintainable.
2. What is Encapsulation?
Answer
Encapsulation is the process of wrapping data and methods together into a single unit (class) and restricting direct access to data.
Real Example
ATM machine hides internal banking details from users.
Interview Answer
Encapsulation is the bundling of data and methods into a single unit while controlling access to the data using access specifiers.
3. What is Abstraction?
Answer
Abstraction means showing only essential information and hiding implementation details.
Real Example
When driving a car, you use the steering wheel and brakes without knowing how the engine works internally.
Interview Answer
Abstraction hides implementation details and exposes only the necessary features to the user.
4. What is Inheritance?
Answer
Inheritance allows one class to acquire properties and methods from another class.
Real Example
Dog inherits properties like eat() and sleep() from Animal.
Interview Answer
Inheritance is a mechanism where a child class acquires properties and behaviors of a parent class.
5. What is Polymorphism?
Answer
Polymorphism means "many forms."
The same function or interface can behave differently depending on the object.
Real Example
A person can be:
Student at college
Son at home
Employee at office
Same person, different behavior.
Interview Answer
Polymorphism allows the same function or interface to perform different actions based on the object.
Medium Questions
6. Encapsulation vs Abstraction?
Encapsulation	Abstraction
Hides data	Hides implementation
Focus on security	Focus on simplicity
Uses access specifiers	Uses abstract classes/interfaces
"""How to protect?"""	"""How to simplify?"""


Interview Answer
Encapsulation protects data from unauthorized access, while abstraction hides implementation complexity from users.
7. Advantages of Inheritance?
Answer
Code Reusability
Reduced Code Duplication
Easy Maintenance
Better Extensibility
Faster Development
Interview Answer
Inheritance improves code reusability and reduces redundancy by allowing child classes to reuse parent class features.
8. Types of Inheritance?
Answer
1. Single Inheritance
A → B
2. Multilevel Inheritance
A → B → C
3. Multiple Inheritance
A
 \
  C
 /
B
4. Hierarchical Inheritance
    A
   / \
  B   C
5. Hybrid Inheritance
Combination of multiple inheritance types.
9. What is Function Overloading?
Answer
Function overloading means having multiple functions with the same name but different parameters.
Example
add(int a, int b)
add(int a, int b, int c)
Interview Answer
Function overloading allows multiple functions with the same name but different parameter lists.
10. What is Function Overriding?
Answer
Function overriding occurs when a child class provides its own implementation of a parent class method.
Example
class Animal
{
public:
    void sound()
    {
    }
};

class Dog : public Animal
{
public:
    void sound()
    {
    }
};
Interview Answer
Function overriding allows a derived class to redefine a method already defined in the base class.
Hard Questions
11. Overloading vs Overriding?
Overloading	Overriding
Same class	Parent-child class
Different parameters	Same parameters
Compile-time	Runtime
No inheritance required	Inheritance required


Interview Answer
Overloading uses the same function name with different parameters, while overriding redefines a parent class function in a child class.
12. Compile-Time vs Runtime Polymorphism?
Compile-Time	Runtime
Function Overloading	Function Overriding
Early Binding	Late Binding
Faster	Slightly slower
Decided by compiler	Decided during execution


Interview Answer
Compile-time polymorphism is resolved by the compiler, whereas runtime polymorphism is resolved while the program is running.
13. Why is Polymorphism Useful?
Answer
Polymorphism provides:
Flexibility
Reusability
Extensibility
Cleaner Code
Example
A single interface can work with different objects.
Interview Answer
Polymorphism allows writing generic and reusable code that can work with different object types.
14. Can We Achieve Runtime Polymorphism Without Virtual Functions?
Answer
In C++, true runtime polymorphism requires virtual functions.
Without virtual functions, function calls are resolved at compile time.
Interview Answer
No. Runtime polymorphism in C++ is achieved using function overriding together with virtual functions.
15. Why is Abstraction Important?
Answer
Abstraction helps:
Reduce complexity
Improve security
Simplify usage
Improve maintainability
Real Example
Using a smartphone without knowing how the processor works internally.
Interview Answer
Abstraction hides unnecessary implementation details and allows users to focus only on essential functionality.
Most Important 5 Questions for Placements
Q1. What are the 4 pillars of OOP?
Encapsulation, Abstraction, Inheritance, Polymorphism.
Q2. Encapsulation vs Abstraction?
Encapsulation hides data, abstraction hides implementation.
Q3. What is Polymorphism?
One interface, many forms.
Q4. Overloading vs Overriding?
Overloading → Compile Time
Overriding → Runtime
Q5. Why is Inheritance Used?
To achieve code reusability and reduce duplication.
These 5 questions alone cover a large portion of OOP theory questions asked in fresher interviews.


