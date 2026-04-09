

# 🧠 OOPs — Day 2

# 🔒 Encapsulation (Very Important)

---

# 🔹 What is Encapsulation?

**Encapsulation means hiding data and allowing access only through functions.**

In simple words:

🔒 **Hide data using `private` variables**
🔓 **Access data using `public` functions**

---

## 📌 Simple Definition (Interview Ready ⭐)

**"Encapsulation is the process of wrapping data and functions together in a single unit and restricting direct access to data."**

---

# 🔹 Why Encapsulation is Used?

Encapsulation is important because:

1️⃣ **Protect Data**
Prevents direct access to variables.

2️⃣ **Improve Security**
Only allowed functions can change data.

3️⃣ **Control Access**
We decide how data is used.

---

# 💻 C++ Example — BankAccount Class

Your code:

```cpp
#include <iostream>
using namespace std;

class BankAccount {

private:

    int balance;

public:

    void setBalance(int b) {

        balance = b;

    }

    int getBalance() {

        return balance;

    }

};

int main() {

    BankAccount acc;

    acc.setBalance(5000);

    cout << "Balance: " << acc.getBalance();

    return 0;
}
```

---

# 🔹 Step-by-Step Explanation

---

## 1️⃣ class BankAccount

```cpp
class BankAccount
```

Creates a **class named BankAccount**.

This class represents a **bank account**.

---

## 2️⃣ Private Variable (Hidden Data)

```cpp
private:

    int balance;
```

`balance` is **private**.

That means:

❌ Cannot access directly
❌ This will NOT work:

```cpp
acc.balance = 5000;  // ❌ Error
```

Because:

👉 Data is **hidden**

This is **Encapsulation**.

---

## 3️⃣ Public Function — setBalance()

```cpp
void setBalance(int b) {

    balance = b;

}
```

This function:

👉 **Sets value** to balance.

Example:

```cpp
acc.setBalance(5000);
```

Now:

```cpp
balance = 5000
```

---

## 4️⃣ Public Function — getBalance()

```cpp
int getBalance() {

    return balance;

}
```

This function:

👉 **Returns value** of balance.

Example:

```cpp
cout << acc.getBalance();
```

Output:

```text
5000
```

---

## 5️⃣ Object Creation

```cpp
BankAccount acc;
```

Creates object:

👉 `acc` is object of `BankAccount`

---

## 6️⃣ Set Value Using Function

```cpp
acc.setBalance(5000);
```

Stores:

```text
balance = 5000
```

---

## 7️⃣ Get Value Using Function

```cpp
cout << acc.getBalance();
```

Prints:

```text
Balance: 5000
```

---

# 🔹 Final Output

```text
Balance: 5000
```

---

# 🔹 Where Encapsulation Happens

Encapsulation happens here:

```cpp
private:
    int balance;
```

Because:

👉 `balance` is hidden
👉 Access only through functions

---

# 🔹 Real-Life Example 🏦

Think of:

**ATM Machine**

You cannot directly access money.

You use:

* PIN
* Withdraw function

Same idea:

* `balance` → private
* `setBalance()` → deposit
* `getBalance()` → check balance

---

# 🔹 Important Interview Questions

These are commonly asked.

---

## ❓ What is Encapsulation?

**Answer:**

**"Encapsulation is the process of hiding data using private variables and accessing it through public functions."**

---

## ❓ Why use private variables?

**Answer:**

To:

* Protect data
* Prevent direct access
* Improve security

---

## ❓ What are Getter and Setter?

| Function       | Meaning             |
| -------------- | ------------------- |
| `setBalance()` | Setter (sets value) |
| `getBalance()` | Getter (gets value) |

---

# 🧪 Day 2 Practice (Do This Yourself)

Very important practice.

---

## Practice 1 — Student Encapsulation

Create class:

```cpp
class Student
```

Add:

Private:

* marks

Public:

* `setMarks(int m)`
* `getMarks()`

Print marks.

---

## Practice 2 — Add Condition ⭐

Modify:

```cpp
setBalance(int b)
```

Add condition:

```cpp
if(b >= 0)
```

So:

❌ Negative balance not allowed.

---

# 🚀 Next Step — Day 3

Next important concept:

# **Inheritance**

