# C++20 Coding Guidelines

This document provides a set of rules and best practices to ensure that our C++ code is modern, safe, and consistent. The following guidelines should be applied when writing new code or refactoring existing code.

---

## 1. Check for Emptiness Using `empty()`

When working with STL containers (such as `std::vector`), prefer checking for emptiness with `empty()` rather than comparing `size()` to 0.

**Incorrect:**
```cpp
std::vector<int> x;
if(x.size()) {
    // ...
}

if(x.size() != 0) {
    // ...
}
```

**Correct:**
```cpp
std::vector<int> x;
if(!x.empty()) {
    // ...
}
```

**Rationale:**  
Using `empty()` is more expressive and often more efficient, as it directly communicates the intent of checking for emptiness.

---

## 2. Prefer List Initialization

Use list initialization (also known as uniform initialization) to avoid narrowing conversions and improve consistency.

**Example:**
```cpp
// Instead of:
int x(5);
std::vector<int> vec(10, 0);

// Use:
int x{5};
std::vector<int> vec{10, 0};
```

**Rationale:**  
List initialization is safer, as it prevents unintended implicit conversions and provides a consistent syntax for initializing variables.

---

## 3. Use `if` Statement with Initializer

Take advantage of C++20’s feature that allows you to initialize a variable within the `if` statement. This can help keep the scope of the variable limited to the `if` block.

**Example:**
```cpp
if(auto it = std::find(container.begin(), container.end(), value); it != container.end()) {
    // Use it safely within this block.
}
```

**Rationale:**  
Using an initializer in an `if` statement can reduce variable scope and improve readability by localizing the variable usage.

---

## 4. Prefer Ranges Over Traditional For-Loops

Leverage the ranges library (from C++20 or the Range-v3 library) to write more declarative and concise loops. This can lead to more readable and maintainable code.

**Example:**
```cpp
#include <ranges>
#include <vector>
#include <iostream>

std::vector<int> numbers = {1, 2, 3, 4, 5};

// Instead of a manual for-loop:
for (const auto& number : numbers) {
    std::cout << number << " ";
}

// Use ranges and views for filtering, transformation, etc.:
auto evenNumbers = numbers | std::ranges::views::filter([](int n) { return n % 2 == 0; });
for (const auto& number : evenNumbers) {
    std::cout << number << " ";
}
```

**Rationale:**  
Ranges can simplify many common operations (like filtering, transformation, and slicing), reducing boilerplate code and making the logic clearer.

---

## 5. Use `0 == x` Instead of `x == 0`

For comparisons with zero, write the literal on the left-hand side. This style (sometimes called “Yoda conditions”) can help prevent accidental assignment errors in some coding environments.

**Example:**
```cpp
// Instead of:
if(x == 0) {
    // ...
}

// Use:
if(0 == x) {
    // ...
}
```

**Rationale:**  
While modern compilers often warn about assignment within conditional expressions, using `0 == x` is an extra safeguard and can improve consistency across the codebase.

---

## 6. Naming Convention for Member Variables

All member variables should be prefixed with `m` to clearly indicate that they belong to an instance of a class.

**Example:**
```cpp
class Example {
public:
    Example(int value)
        : mValue{value} {}  // List initialization is used here

    int getValue() const noexcept { return mValue; }

private:
    int mValue;  // Member variable prefixed with 'm'
};
```

**Rationale:**  
Prefixing member variables with `m` helps distinguish them from local variables and function parameters, improving code readability and maintainability.

---
