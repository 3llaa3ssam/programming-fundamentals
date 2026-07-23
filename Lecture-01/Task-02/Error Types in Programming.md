# Error Types in Programming

Every programming error falls into one of three broad categories, distinguished by **when** they occur and **how** they're detected: Syntax Errors, Runtime Errors, and Logical Errors.

---

## 1. Syntax Error

### Definition
A **syntax error** occurs when code violates the grammatical rules of the programming language. The compiler (or interpreter) cannot parse the code, so the program fails *before it ever runs*.

### Example (C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello World"
    return 0;
}
```

**Error:** Missing semicolon (`;`) after the `cout` statement. The compiler stops here and reports an error, usually pointing at or near the line where the `;` was expected.

### Other Common Causes
- Mismatched or missing brackets `{ }`, `( )`, `[ ]`
- Misspelled keywords (e.g., `retrun` instead of `return`)
- Missing quotation marks around strings
- Incorrect operator usage

---

## 2. Runtime Error

### Definition
A **runtime error** occurs *after* the program has compiled successfully, but something goes wrong while it is actually executing — causing a crash or abnormal termination.

### Example (C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10;
    int b = 0;
    cout << a / b;
    return 0;
}
```

**Error:** Division by zero. This compiles fine because the compiler has no way of knowing that `b` will be `0` at runtime — the crash only happens when the division actually executes.

### Other Common Causes
- Null or invalid pointer dereference
- Array index out of bounds
- Stack overflow (e.g., infinite recursion)
- Running out of memory
- File not found when trying to open a file

---

## 3. Logical Error

### Definition
A **logical error** occurs when the program compiles and runs without crashing, but produces incorrect output because the algorithm or logic itself is flawed. These are the hardest to catch, since there's no error message — the program "works," it's just wrong.

### Example (C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int length = 5;
    int width = 3;
    int area = length + width;  // should be length * width
    cout << area;
    return 0;
}
```

**Error:** The area of a rectangle should be calculated as `length * width` (= 15), not `length + width` (= 8). The program runs successfully and prints a number — it just prints the *wrong* one.

### Other Common Causes
- Incorrect formula or algorithm
- Off-by-one errors in loops
- Wrong comparison operator (`<` instead of `<=`)
- Incorrect variable used in a calculation

---

## Summary Table

| Error Type | When Detected | Result | Detected By |
|---|---|---|---|
| **Syntax Error** | Before execution (compile time) | Program fails to compile | Compiler / interpreter |
| **Runtime Error** | During execution | Program crashes or stops unexpectedly | OS / runtime environment |
| **Logical Error** | During execution | Program runs, but output is incorrect | Only by testing / human review |

---

## Key Takeaway

Syntax and runtime errors **announce themselves** — a compiler error message or a crash tells you something is wrong. Logical errors are **silent** — the program runs cleanly, so the only way to catch them is by carefully checking the actual output against the expected output (i.e., through testing, tracing, or code review).
