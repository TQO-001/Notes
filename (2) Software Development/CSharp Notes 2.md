## **1️⃣ C# Basics**

> These are the fundamental building blocks to get any C# program up and running.

---

### **1.1 Comments**

|Syntax|Description|
|---|---|
|`//`|Single-line comment|
|`/* ... */`|Multi-line comment|
|`///`|XML documentation comment|

```csharp
// This is a single-line comment

/* This is
   a multi-line comment */

/// <summary>
/// This is an XML doc comment
/// </summary>
public void MyMethod() { }
```

---
### **1.2 `using` Directives & Namespaces

|Concept|Description|
|---|---|
|`using`|Lets you **import** other namespaces so you can use their classes/methods without fully qualifying them.|
|Namespace block|Groups **related code** (classes, interfaces, enums, etc.) under a **unique name** to avoid conflicts.|

#### ✅ Why Namespaces?

In C#, a **namespace** is like a **folder structure** for your code. It **prevents name clashes** when different libraries or parts of your app have the same class names.

For example:

```csharp
namespace MyApp.Services {
    class EmailSender { }
}

namespace MyApp.Models {
    class EmailSender { }
}
```

> Both classes are called `EmailSender`, but their namespaces keep them separate.

---

#### ✅ What `using` Does

If you want to use `Console.WriteLine()`, you need the `System` namespace:

```csharp
using System;  // Now you can use Console directly

Console.WriteLine("Hello");
```

Without `using`:

```csharp
System.Console.WriteLine("Hello");
```

---

#### ✅ Nested Namespaces

You can **nest namespaces** for better organization:

```csharp
namespace MyApp {
    namespace Utilities {
        class Logger { }
    }
}
```

Or with modern syntax (C# 10+):

```csharp
namespace MyApp.Utilities;

class Logger { }
```

---

#### ✅ Custom Namespaces

Good practice is to use:

`<Company>.<Project>.<Feature>`

Example:

```csharp
namespace LaughTale.Finance.Invoicing {
    class InvoiceManager { }
}
```

---

> **Side‑Note:**  
> Namespaces don’t affect how the code runs—they are just **organizational**. But they **matter a lot** when your app grows or when using external libraries.

---
### **1.3 `Main` Method & Program Skeleton**

|Element|Description|
|---|---|
|`static void Main()`|Entry point of a C# console app|
|`args`|Array of command-line arguments|

```csharp
class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("C# App Started");
        Console.WriteLine("Args count: " + args.Length);
    }
}
```

#### Modern C# Shortcut (Top-Level Statements)

```csharp
Console.WriteLine("Hello World!");
```

> **Side‑Note:**  
> As of **C# 9**, you can omit `class`/`Main` boilerplate for **simple apps** (like scripts or quick tests).

---

## **2️⃣ Data Types & Variables**

> C# is **strongly typed**, meaning every variable must have a declared type.

---

### **2.1 Value Types**

|Type|Example|Description|
|---|---|---|
|`int`|`int age = 30;`|Integer (whole numbers)|
|`double`|`double pi = 3.14;`|Floating point (double precision)|
|`bool`|`bool isActive = true;`|Boolean (true/false)|
|`char`|`char grade = 'A';`|Single character (Unicode)|
|`struct`|See below|Custom value type (like a lightweight class)|

```csharp
int age = 25;
double score = 89.5;
bool isAvailable = true;
char letter = 'C';

// Struct example
struct Point {
    public int X;
    public int Y;
}
```

> **Side‑Note:**  
> **Value types** are stored **directly in memory (stack)** and hold their own data.

---

### **2.2 Reference Types**

|Type|Example|Description|
|---|---|---|
|`string`|`string name = "Thulani";`|Sequence of characters|
|`object`|`object obj = 42;`|Base type for all other types|
|Arrays|`int[] nums = {1, 2, 3};`|Fixed-size collection of elements of the same type|

```csharp
string message = "Hello, World!";
object something = 100;
int[] numbers = new int[] {1, 2, 3};
```

> **Brief:**  
> **Reference types** store a **reference (pointer) to the data** in memory (heap).  
> Even simple types like `string` are **immutable reference types**—modifying them creates a new object.

---

### **2.3 Nullable Types**

|Syntax|Description|
|---|---|
|`int?`|Integer that can also be `null`|
|`bool?`|Boolean that can also be `null`|

```csharp
int? score = null;
bool? isChecked = null;

if (score.HasValue)
    Console.WriteLine(score.Value);
```

> **Side‑Note:**  
> Only **value types** need `?` to be nullable. Reference types are nullable by default.

---

### **2.4 Constants vs Read-Only**

|Feature|`const`|`readonly`|
|---|---|---|
|Set When?|Compile-time|Run-time (in constructor)|
|Scope|Always static|Can be instance or static|
|Usage|Must know value at compile time|Can be set dynamically at construction|

```csharp
const double Pi = 3.14159;  // Must be known at compile time

readonly DateTime createdAt;

public MyClass() {
    createdAt = DateTime.Now;  // Set at runtime (constructor)
}
```

> **Tip:**  
> Use `const` for **unchanging universal values** (e.g., Pi, tax rate).  
> Use `readonly` when the value is **set once but not known at compile time**.

---

## **3️⃣ Operators**

> C# has a rich set of operators for performing calculations, comparisons, and handling nullability smartly.

---

### **3.1 Arithmetic & Assignment**

| Operator | Example     | Description         |
| -------- | ----------- | ------------------- |
| `+`      | `x + y`     | Addition            |
| `-`      | `x - y`     | Subtraction         |
| `*`      | `x * y`     | Multiplication      |
| `/`      | `x / y`     | Division            |
| `%`      | `x % y`     | Modulus (remainder) |
| `++`     | `x++ / ++x` | Increment           |
| `--`     | `x-- / --x` | Decrement           |
| `=`      | `x = 5`     | Assignment          |
| `+=`     | `x += 3`    | Add and assign      |
| `-=`     | `x -= 2`    | Subtract and assign |
| `*=`     | `x *= 4`    | Multiply and assign |
| `/=`     | `x /= 2`    | Divide and assign   |

```csharp
int a = 10;
a += 5;  // 15
a++;     // 16
int b = a % 3;  // 1
```

---

### **3.2 Comparison & Logical**

|Operator|Example|Description|
|---|---|---|
|`==`|`x == y`|Equal to|
|`!=`|`x != y`|Not equal to|
|`<` `>`|`x < y`, `x > y`|Less than / greater than|
|`<=` `>=`|`x <= y`, `x >= y`|Less than or equal / greater or equal|
|`&&`|`x && y`|Logical AND|
|`||`|
|`!`|`!x`|Logical NOT|

```csharp
bool isAdult = age >= 18;
bool canVote = isAdult && isCitizen;
```

---

### **3.3 Ternary (`?:`) & Null-Coalescing (`??`)**

|Operator|Example|Description|
|---|---|---|
|`?:` (ternary)|`var status = age > 18 ? "Adult" : "Minor";`|Shorthand for if/else|
|`??`|`string name = inputName ?? "Default";`|Returns left if not null; otherwise right|

```csharp
string result = (score >= 50) ? "Pass" : "Fail";

string userName = input ?? "Guest";
```

> **Brief:**  
> The **ternary operator** condenses an `if-else` into a single line.  
> The **null-coalescing operator** is handy to provide defaults when a value may be `null`.

---

### **3.4 Null-Conditional (`?.`) & Other Special Operators**

|Operator|Example|Description|
|---|---|---|
|`?.`|`person?.Name`|Accesses property only if the object is not null|
|`??=`|`x ??= y;`|Assigns `y` if `x` is null|
|`is`|`if (obj is string)`|Type checking|
|`as`|`var s = obj as string;`|Safe casting (returns null if incompatible)|
|`nameof`|`nameof(myVar)`|Returns string name of the variable|
|`sizeof`|`sizeof(int)`|Gets size (in bytes) of a value type|
|`typeof`|`typeof(string)`|Gets the `Type` object|

```csharp
// Null-conditional
Console.WriteLine(person?.Name);

// Null-coalescing assignment
name ??= "Unknown";

// Type checking
if (item is string s) {
    Console.WriteLine($"String length: {s.Length}");
}

// nameof
Console.WriteLine(nameof(age));  // Prints: age
```

> **Side‑Note:**  
> The **null-conditional operator** (`?.`) **avoids null reference exceptions** by stopping the call chain if anything is null. Very handy when working with nested objects.

---
## **4️⃣ Control Flow**

> Control flow determines how your program makes decisions and repeats tasks.

---

### **4.1 `if` / `else if` / `else`**

```csharp
if (age < 13) {
    Console.WriteLine("Child");
}
else if (age < 20) {
    Console.WriteLine("Teen");
}
else {
    Console.WriteLine("Adult");
}
```

- **`if`:** Executes a block if the condition is true.
- **`else if`:** Adds additional conditions.
- **`else`:** Catches anything not already matched.

✅ **Tip:** Conditions are always boolean expressions.

---

### **4.2 `switch` / Pattern Matching**

#### 🔹 Basic `switch`

```csharp
switch (day) {
    case 1:
        Console.WriteLine("Monday");
        break;
    case 2:
        Console.WriteLine("Tuesday");
        break;
    default:
        Console.WriteLine("Other day");
        break;
}
```

#### 🔹 Switch Expressions (Modern)

```csharp
string result = day switch {
    1 => "Monday",
    2 => "Tuesday",
    _ => "Other day"
};
```

#### 🔹 Pattern Matching (C# 8+)

```csharp
object obj = 5;
switch (obj) {
    case int i when i > 0:
        Console.WriteLine($"Positive int: {i}");
        break;
    case string s:
        Console.WriteLine($"String: {s}");
        break;
    default:
        Console.WriteLine("Other type");
        break;
}
```

✅ **Tip:** Pattern matching allows checks based on **type** and **conditions**—super useful when dealing with different object types.

---

### **4.3 Loops (`for`, `foreach`, `while`, `do…while`)**

#### 🔹 `for`

```csharp
for (int i = 0; i < 5; i++) {
    Console.WriteLine(i);
}
```

- Best when you know **how many times** to loop.

---

#### 🔹 `foreach`

```csharp
foreach (var item in items) {
    Console.WriteLine(item);

```

- Loops through each **element** of a collection/array.

---

#### 🔹 `while`

```csharp
int count = 0;
while (count < 3) {
    Console.WriteLine(count);
    count++;
}
```

- Loops **while condition is true.**
    

---

#### 🔹 `do…while`

```csharp
int number;
do {
    Console.WriteLine("Enter a number:");
    number = Convert.ToInt32(Console.ReadLine());
} while (number != 0);
```

- Always runs **at least once,** then checks condition.
    

---

#### ✅ **Quick Recap**
- Use **`if/else`** for straightforward decisions.
- **`switch`** (especially with pattern matching) handles multiple discrete cases cleanly.
- Loops repeat tasks:
    - `for`: known count
    - `foreach`: collections
    - `while`: unknown count        
    - `do…while`: at least once
---
## **5️⃣ Methods & Parameters**

> Methods define **reusable blocks of code** that perform tasks or calculations.

---

### **5.1 Defining & Calling Methods**

```csharp
void Greet(string name) {
    Console.WriteLine($"Hello, {name}!");
}

// Calling
Greet("Thulani");
```

- **Return type + method name + parameters.**
    
- Methods must be inside a **class**.
    

#### Return Example

```csharp
int Add(int a, int b) {
    return a + b;
}
int sum = Add(5, 3);
```

---

### **5.2 Method Overloading**

> Define multiple methods with the **same name but different parameters.**

```csharp
void Print(string text) {
    Console.WriteLine(text);
}

void Print(int number) {
    Console.WriteLine(number);
}
```

✅ **Tip:** Overloading helps create intuitive APIs.

---
### **5.3 Parameter Modifiers: `ref`, `out`, `in`, `params`, Optional**

> C# allows **fine control** over how arguments are passed to methods using modifiers. These help when you need **multiple return values**, **efficient memory use**, or **flexible inputs.**

#### 🔸 `ref` (Reference)

- Passes an argument **by reference.**
    
- The variable **must be initialized before** being passed.
    
- Changes inside the method **affect the original value.**
    

```csharp
void DoubleValue(ref int x) {
    x *= 2;
}

int a = 5;
DoubleValue(ref a);
Console.WriteLine(a);  // 10
```

---

#### 🔸 `out` (Output)

- Also passes **by reference,** but is designed for **output.**
    
- The variable **doesn't need to be initialized.**
    
- The method **must assign a value** before returning.
    

```csharp
void GetValues(out int a, out int b) {
    a = 10;
    b = 20;
}

int x, y;
GetValues(out x, out y);
Console.WriteLine(x);  // 10
Console.WriteLine(y);  // 20
```

✅ **Common Use:**  
`int.TryParse(string, out int result);`

---

#### 🔸 `in` (Read-Only Reference)

- Passes **by reference** but **cannot be modified** inside the method.
    
- Useful for **large structs** to avoid copying, but keep them **immutable.**
    

```csharp
void PrintLength(in string text) {
    Console.WriteLine(text.Length);
}

string msg = "Hello";
PrintLength(msg);
```

---

#### 🔸 `params` (Variable Arguments)

- Allows you to pass a **variable number of parameters** as an array.
    
- Must be the **last parameter** in the method.
    

```csharp
void SumAll(params int[] numbers) {
    Console.WriteLine(numbers.Sum());
}

SumAll(1, 2, 3, 4);  // 10
SumAll();            // 0
```

---

#### 🔸 Optional Parameters

- You can assign **default values** to parameters.
    
- If no argument is passed, the **default is used.**
    

```csharp
void Log(string message = "Default log", int level = 1) {
    Console.WriteLine($"{level}: {message}");
}

Log();                     // 1: Default log
Log("Custom message", 3);  // 3: Custom message
```

✅ **Named arguments** can make calls clearer:

```csharp
Log(level: 5, message: "Important");
```

---

|Modifier|Must Initialize Before?|Can Be Changed?|Use Case|
|---|---|---|---|
|`ref`|Yes|Yes (mutates)|Modify existing variable|
|`out`|No|Yes (must assign)|Return multiple values|
|`in`|Yes|No (read-only)|Optimize large structs (no copy, no change)|
|`params`|N/A|N/A|Pass flexible-length arguments|
|Optional|N/A|N/A|Simplify method calls with default values|

---

> **Side‑Note:**  
> `ref` and `out` are sometimes misunderstood—**both are by-reference**, but `out` is specifically for **output-only**, while `ref` assumes the variable has a starting value.

---

### **5.4 Expression-Bodied Members & Local Functions**

#### 🔹 Expression-Bodied Members

> A **short-hand** for methods (and other members) that **only return a value or perform a single expression.**

##### Example: Method

```csharp
int Square(int x) => x * x;
```

##### Property

```csharp
public int Age { get; } = 30;
public string Name => "Thulani";
```

##### Constructor

```csharp
class Person {
    public string Name;
    public Person(string name) => Name = name;
}
```

✅ **Where to Use:**

- Small, **single-line** methods.
    
- Properties that just return a **computed value.**
    
- Keeping code clean and **concise.**
    

---

#### 🔹 Local Functions

> Functions defined **inside another method.** Helps you **encapsulate helper logic** that's only relevant in that scope.

##### Example

```csharp
void Process() {
    Console.WriteLine("Processing...");

    int Multiply(int a, int b) {
        return a * b;
    }

    int result = Multiply(3, 4);
    Console.WriteLine(result);
}
```

- Local functions can:
    
    - Access **variables** from the outer method.
        
    - Be **recursive.**
        
    - Help avoid polluting the outer class.
        

✅ **When to Use:**

- **Helper methods** that shouldn’t be exposed to the whole class.
    
- **Keep related logic together.**
    

---

> **Side‑Note:**  
> Local functions can also have **expression bodies:**

```csharp
void DoWork() {
    int Square(int x) => x * x;
    Console.WriteLine(Square(5));
}
```
---
## **6️⃣ Collections & Generics**

---

### **6.1 Arrays**

> Arrays are **fixed-size**, strongly-typed collections that store elements of the same type. They are the most basic collection type in C#.

#### Declaration & Initialization

```csharp
// Declare an array of integers
int[] numbers = new int[5];

// Initialize with values
string[] fruits = { "Apple", "Banana", "Cherry" };
```

#### Accessing Elements

```csharp
int firstNumber = numbers[0];  // Access first element (index 0)
fruits[1] = "Blueberry";       // Modify second element
```

#### Multi-Dimensional Arrays

```csharp
// Declare a 2D array (matrix)
int[,] matrix = new int[2, 3] {
    {1, 2, 3},
    {4, 5, 6}
};

// Access a specific element
int val = matrix[1, 2];  // 6
```

#### Arrays Length

```csharp
int length = numbers.Length;  // Gets the length of the array
```

---

### **6.2 `List<T>`, `Dictionary<TKey,TValue>`, etc.**

> **Collections** in C# like `List<T>` and `Dictionary<TKey,TValue>` are **dynamic** and provide **flexibility** with more functionality than arrays. They are part of the **System.Collections.Generic** namespace.

#### 🔹 `List<T>`

- **Dynamic collection** for storing objects of any type.
    
- Automatically **resizes** when elements are added or removed.
    
- Provides easy access to collection methods like **Add()**, **Remove()**, **Contains()**, etc.
    

```csharp
List<string> names = new List<string> { "Alice", "Bob", "Charlie" };

// Adding and accessing elements
names.Add("David");
string firstName = names[0];  // Alice

// Removing an element
names.Remove("Bob");
```

#### 🔹 `Dictionary<TKey, TValue>`

- Stores **key-value pairs** where each **key** is unique.
    
- Offers fast lookups by key.
    

```csharp
Dictionary<string, int> ageDictionary = new Dictionary<string, int> {
    { "Alice", 30 },
    { "Bob", 25 }
};

// Adding a new key-value pair
ageDictionary["Charlie"] = 35;

// Accessing values by key
int bobAge = ageDictionary["Bob"];  // 25

// Checking for key existence
if (ageDictionary.ContainsKey("Alice")) {
    Console.WriteLine("Alice is in the dictionary.");
}
```

#### 🔹 `Queue<T>` & `Stack<T>`

- **Queue** follows **First-In-First-Out (FIFO)** order, used for **waiting lines**.
    
- **Stack** follows **Last-In-First-Out (LIFO)** order, used for **reversing order** or **undo actions**.
    

```csharp
Queue<string> queue = new Queue<string>();
queue.Enqueue("First");
queue.Enqueue("Second");
Console.WriteLine(queue.Dequeue());  // First

Stack<string> stack = new Stack<string>();
stack.Push("Top");
stack.Push("Middle");
Console.WriteLine(stack.Pop());  // Middle
```

---

### **6.3 Defining Generic Classes & Methods**

> Generics in C# allow you to define types that can work with **any data type** while providing type safety. You can define **generic classes**, **methods**, and **interfaces**.

#### 🔹 Generic Method

```csharp
// A generic method to swap two values
void Swap<T>(ref T a, ref T b) {
    T temp = a;
    a = b;
    b = temp;
}

// Usage
int x = 5, y = 10;
Swap(ref x, ref y);
Console.WriteLine(x);  // 10
Console.WriteLine(y);  // 5
```

#### 🔹 Generic Class

```csharp
// A generic class for holding pairs of values
public class Pair<T, U> {
    public T First { get; set; }
    public U Second { get; set; }

    public Pair(T first, U second) {
        First = first;
        Second = second;
    }
}

// Usage
Pair<int, string> pair = new Pair<int, string>(1, "apple");
Console.WriteLine(pair.First);   // 1
Console.WriteLine(pair.Second);  // apple
```

#### 🔹 Constraints

You can add **constraints** to generic types, restricting what types can be used.

```csharp
// T must be a class that implements IComparable
public class Sortable<T> where T : IComparable {
    public void Sort(T[] array) {
        Array.Sort(array);
    }
}
```

---

### **6.4 Quick-lookup Table of Common Collection APIs**

|Collection Type|Common Methods|Example Usage|
|---|---|---|
|`List<T>`|`Add()`, `Remove()`, `Contains()`, `Insert()`, `Sort()`, `Clear()`|`list.Add(item)`, `list.RemoveAt(index)`|
|`Dictionary<TKey,TValue>`|`Add()`, `Remove()`, `ContainsKey()`, `TryGetValue()`, `Keys`, `Values`|`dict["key"] = value`, `dict.ContainsKey(key)`|
|`Queue<T>`|`Enqueue()`, `Dequeue()`, `Peek()`, `Clear()`|`queue.Enqueue(item)`, `queue.Dequeue()`|
|`Stack<T>`|`Push()`, `Pop()`, `Peek()`, `Clear()`|`stack.Push(item)`, `stack.Pop()`|
|`HashSet<T>`|`Add()`, `Remove()`, `Contains()`|`set.Add(item)`, `set.Contains(item)`|

---

### **Side Notes:**

- **Why Use Generics?**
    
    - **Type safety**: C# checks that you’re using the correct type at compile-time.
        
    - **Performance**: No need for boxing/unboxing or casting.
        
    - **Reusability**: Define one method or class that works with many types.
        
- **`var` vs `List<T>`**: You can use `var` to implicitly define collections but use `List<T>` for type safety and code clarity.

---

## **7️⃣ Exception Handling**

> Exception handling in C# allows you to **catch** errors (exceptions) that occur during program execution, giving you the chance to **handle** them gracefully, prevent crashes, and provide meaningful error messages to users.

---

### **7.1 `try` / `catch` / `finally`**

> The `try` block allows you to write code that may throw exceptions, and the `catch` block allows you to handle those exceptions when they occur. The `finally` block is optional and allows you to execute code after the `try` block, whether or not an exception was thrown.

#### Syntax:

```csharp
try {
    // Code that may throw an exception
    int result = 10 / 0;  // Division by zero will throw an exception
} catch (DivideByZeroException ex) {
    // Code to handle the exception
    Console.WriteLine("Error: " + ex.Message);
} finally {
    // Code that will run after the try/catch block, regardless of exception
    Console.WriteLine("Cleanup code or logging here.");
}
```

#### **Flow**:

1. **`try`** block executes code that may cause an exception.
    
2. If an exception occurs, the **`catch`** block catches it and handles it.
    
3. The **`finally`** block runs no matter what, even if there’s an exception.
    

#### Multiple `catch` blocks:

You can have multiple `catch` blocks to handle different types of exceptions:

```csharp
try {
    // Some code that may throw different exceptions
    string[] arr = new string[2];
    Console.WriteLine(arr[5]);  // This will throw IndexOutOfRangeException
} catch (IndexOutOfRangeException ex) {
    Console.WriteLine("Index out of range: " + ex.Message);
} catch (Exception ex) {
    Console.WriteLine("General error: " + ex.Message);
}
```

#### **Best Practice:**

- Always catch **specific exceptions** first to handle known cases.
    
- Use **general exceptions** (like `Exception`) as the last `catch` block to handle unexpected errors.
    

---

### **7.2 `throw` & Re-throwing**

> The `throw` keyword is used to **explicitly throw exceptions**. You can throw an exception manually to indicate that something went wrong. You can also **re-throw** an exception from within a `catch` block.

#### Throwing an exception:

```csharp
if (age < 0) {
    throw new ArgumentException("Age cannot be negative");
}
```

#### Re-throwing an exception:

When you catch an exception, you might want to **log** it, and then **re-throw** it for higher-level handling.

```csharp
try {
    // Some code that throws an exception
    throw new InvalidOperationException("Something went wrong");
} catch (InvalidOperationException ex) {
    Console.WriteLine("Logging exception: " + ex.Message);
    throw;  // Re-throws the caught exception
}
```

> **Note:** The `throw` statement inside a `catch` block without specifying an exception re-throws the **same exception** that was caught.

---

### **7.3 Custom Exceptions**

> You can create **custom exception types** by inheriting from the built-in `Exception` class. Custom exceptions are useful for handling application-specific errors more clearly.

#### Syntax for Custom Exception:

```csharp
// Define a custom exception
public class InvalidAgeException : Exception {
    public InvalidAgeException() : base("Invalid age value provided.") { }

    public InvalidAgeException(string message) : base(message) { }

    public InvalidAgeException(string message, Exception inner) : base(message, inner) { }
}

// Usage
try {
    throw new InvalidAgeException("Age must be greater than 0.");
} catch (InvalidAgeException ex) {
    Console.WriteLine(ex.Message);
}
```

#### **Important Considerations**:

1. **`base(message)`**: Passes the error message to the base `Exception` class.
    
2. **`innerException`**: You can pass another exception to give more context about the cause of the error.
    

#### **When to Use Custom Exceptions**:

- When the error is domain-specific and needs a unique type of exception for better clarity (e.g., `InvalidAgeException`, `OrderNotFoundException`).
    
- When you want to add additional properties or logic (like tracking error codes or logging information).
    

---

### **Best Practices for Exception Handling**

1. **Handle only expected exceptions**: Catch exceptions that you know may occur (e.g., file not found, invalid input), and let the unexpected ones propagate.
    
2. **Don’t catch general `Exception` unless necessary**: Catch specific exceptions first to avoid swallowing unexpected errors.
    
3. **Use custom exceptions**: For business logic-related errors, create custom exceptions that provide more meaningful information.
    
4. **Don’t use exceptions for control flow**: Exceptions should be used for truly **exceptional** situations, not for regular logic flow.
    

---

### **Side Notes:**

- **Performance**: Handling exceptions can be slow, so avoid wrapping code in a `try-catch` block unless there’s a reasonable chance of an exception occurring.
    
- **Logging**: Always log exceptions for troubleshooting purposes, especially for custom exceptions.
    
- **`finally` block**: Great for resource cleanup (e.g., closing files, releasing database connections) that should happen regardless of whether an exception was thrown.
    

---
## **8️⃣ Object-Oriented Programming**

> Object-Oriented Programming (OOP) is a paradigm that organizes software design around data (objects) and methods (functions) that operate on that data. In C#, OOP concepts include defining classes, objects, inheritance, polymorphism, and encapsulation.

---

### **8.1 Defining Classes & Objects**

> A **class** is a blueprint for creating objects, while an **object** is an instance of a class. Classes define properties (attributes) and methods (functions).

#### Defining a Class:

```csharp
public class Person {
    public string Name { get; set; }
    public int Age { get; set; }

    public void Greet() {
        Console.WriteLine($"Hello, my name is {Name} and I am {Age} years old.");
    }
}
```

#### Creating an Object (Instance):

```csharp
Person person1 = new Person();
person1.Name = "John";
person1.Age = 30;
person1.Greet();  // Output: Hello, my name is John and I am 30 years old.
```

> **Key Points**:
> 
> - A class defines the **structure** of the object.
>     
> - An object is an **instance** of the class with specific data.
>     

---

### **8.2 Properties (Auto-props, Backing Fields)**

> Properties are used to define the state of an object. You can either use **auto-implemented properties** or provide your own **backing fields** to encapsulate data.

#### Auto-implemented Properties:

```csharp
public class Person {
    public string Name { get; set; }  // Auto-implemented property
}
```

#### Backing Fields:

```csharp
public class Person {
    private string _name;

    public string Name {
        get { return _name; }
        set { _name = value; }
    }
}
```

> **Auto-Props**: C# provides auto-implemented properties for simple cases where you don’t need custom logic in the getter/setter.  
> **Backing Fields**: Use when you need custom logic in the getter/setter or need to perform additional work on assignment.

---

### **8.3 Inheritance, `base` & `override`**

> **Inheritance** allows a class to **inherit** members (methods, properties) from another class. The **`base`** keyword is used to refer to the base class, and **`override`** allows modifying a method from the base class in the derived class.

#### Inheritance:

```csharp
public class Animal {
    public string Name { get; set; }
    public void Speak() {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal {
    public void Bark() {
        Console.WriteLine("Woof!");
    }

    // Override base method
    public override void Speak() {
        Console.WriteLine("Bark");
    }
}
```

#### Using `base`:

```csharp
public class Dog : Animal {
    public override void Speak() {
        base.Speak();  // Calls the base class method
        Console.WriteLine("Bark");
    }
}
```

> **Key Points**:
> 
> - **Inheritance** allows reusing code from base classes.
>     
> - **`base`** accesses base class members.
>     
> - **`override`** provides custom implementations for inherited methods.
>     

---

### **8.4 Polymorphism & Abstract Classes**

> **Polymorphism** allows objects of different types to be treated as objects of a common base type. This is often implemented through **abstract classes** and **interfaces**.

#### Abstract Classes:

An **abstract class** can’t be instantiated and may contain abstract methods (methods without implementation).

```csharp
public abstract class Animal {
    public abstract void Speak();
}

public class Dog : Animal {
    public override void Speak() {
        Console.WriteLine("Woof!");
    }
}
```

> **Key Points**:
> 
> - **Polymorphism** allows derived classes to implement their own versions of a method.
>     
> - **Abstract classes** provide a common base but force derived classes to implement specific methods.
>     

---

### **8.5 Interfaces**

> An **interface** defines a contract for classes without providing implementation. Classes that implement an interface must provide implementation for all its members.

```csharp
public interface IDriveable {
    void Drive();
}

public class Car : IDriveable {
    public void Drive() {
        Console.WriteLine("Car is driving");
    }
}
```

> **Key Points**:
> 
> - Interfaces define **what** a class should do (contract), but not **how** it should do it.
>     
> - A class can implement **multiple interfaces**.
>     

---

### **8.6 Access Modifiers & Encapsulation**

> **Encapsulation** is the concept of **hiding the internal state** of an object and only exposing functionality through methods or properties. **Access modifiers** control the visibility of members.

#### Access Modifiers:

- **`public`**: Accessible from anywhere.
    
- **`private`**: Accessible only within the class.
    
- **`protected`**: Accessible within the class and derived classes.
    
- **`internal`**: Accessible within the same assembly.
    
- **`protected internal`**: Accessible within the same assembly and derived classes.
    

```csharp
public class Person {
    private string name;  // Private access
    public int Age { get; set; }  // Public access
}
```

> **Key Points**:
> 
> - **Encapsulation** ensures internal details are hidden and only necessary information is exposed.
>     
> - Use access modifiers to enforce boundaries and restrict access to object data.
>     

---

### **8.7 `struct` vs `class`**

> **`struct`** and **`class`** are both types in C#, but they behave differently:

- **`struct`** is a **value type**, meaning it is copied when passed around.
    
- **`class`** is a **reference type**, meaning it is passed by reference.
    

#### Struct:

```csharp
public struct Point {
    public int X;
    public int Y;
}
```

#### Class:

```csharp
public class Point {
    public int X;
    public int Y;
}
```

> **Key Differences**:

- **Value types** (`struct`) are stored on the stack, **reference types** (`class`) on the heap.
    
- **`struct`** objects are copied when assigned or passed to a method, whereas **`class`** references are shared.
    

---

### **8.8 Static Members, `sealed` & `partial` Classes**

> **Static members** belong to the class rather than any instance of the class. **`sealed`** classes cannot be inherited, and **`partial`** classes allow a class to be split across multiple files.

#### Static Members:

```csharp
public class Calculator {
    public static int Add(int a, int b) {
        return a + b;
    }
}

int result = Calculator.Add(5, 3);  // No need to create an instance
```

#### Sealed Classes:

```csharp
public sealed class Car {  
    // This class cannot be inherited
}
```

#### Partial Classes:

```csharp
// File 1
public partial class Person {
    public string Name { get; set; }
}

// File 2
public partial class Person {
    public int Age { get; set; }
}
```

> **Key Points**:
> 
> - **Static members** are shared among all instances of a class.
>     
> - **`sealed`** prevents inheritance.
>     
> - **`partial`** allows splitting a class definition into multiple files.
>     

---
Here is your **Delegates, Events & Lambdas** section with detailed notes, focusing on each concept and how they work in C#.

---

## **9️⃣ Delegates, Events & Lambdas**

> **Delegates**, **events**, and **lambdas** are powerful features in C# that enable flexible, event-driven programming. They allow you to pass methods as parameters, handle events in a decoupled way, and write concise, functional-style code.

---

### **9.1 Declaring & Using Delegates**

> A **delegate** is a type that represents a method signature. It is used to store references to methods and allows calling them through the delegate object. Delegates are essential for implementing event handling and callback mechanisms.

#### Declaring a Delegate:

```csharp
public delegate int Operation(int x, int y);
```

#### Using a Delegate:

```csharp
// Method that matches the delegate signature
public int Add(int x, int y) {
    return x + y;
}

Operation operation = new Operation(Add);
Console.WriteLine(operation(5, 3));  // Output: 8
```

> **Key Points**:
> 
> - A **delegate** type is declared with a method signature.
>     
> - A delegate can be instantiated to point to a method that matches its signature.
>     
> - Delegates allow methods to be passed around as parameters.
>     

---

### **9.2 Event Patterns (`event` keyword)**

> **Events** provide a way for a class to notify other classes when something important happens. They are typically used in event-driven programming (e.g., button click events, data change events). C# uses the **`event`** keyword to declare events.

#### Declaring an Event:

```csharp
public delegate void Notify();  // Delegate type

public class Publisher {
    public event Notify OnChange;  // Event declaration

    public void TriggerEvent() {
        OnChange?.Invoke();  // Trigger the event (safe invocation)
    }
}
```

#### Subscribing to an Event:

```csharp
public class Subscriber {
    public void HandleEvent() {
        Console.WriteLine("Event triggered!");
    }
}

Publisher publisher = new Publisher();
Subscriber subscriber = new Subscriber();

// Subscribe to the event
publisher.OnChange += subscriber.HandleEvent;

// Trigger the event
publisher.TriggerEvent();  // Output: Event triggered!
```

> **Key Points**:
> 
> - The **`event`** keyword encapsulates a delegate, ensuring the event can only be invoked by the declaring class.
>     
> - **Subscribers** add methods to the event (via `+=`) and remove them (via `-=`).
>     
> - Events promote **decoupling**, allowing classes to remain unaware of specific event handlers.
>     

---

### **9.3 Lambda Expressions**

> **Lambda expressions** provide a concise way to write anonymous methods (methods without a name). They are commonly used with delegates, LINQ queries, and events. Lambdas enable functional programming patterns and are more compact than regular method declarations.

#### Syntax:

```csharp
(x, y) => x + y;  // A lambda expression that adds two numbers
```

#### Example with Delegates:

```csharp
public delegate int Operation(int x, int y);

Operation add = (x, y) => x + y;
Console.WriteLine(add(5, 3));  // Output: 8
```

#### Example with LINQ:

```csharp
var numbers = new List<int> { 1, 2, 3, 4, 5 };
var evenNumbers = numbers.Where(n => n % 2 == 0);  // Using a lambda in LINQ
Console.WriteLine(string.Join(", ", evenNumbers));  // Output: 2, 4
```

> **Key Points**:
> 
> - Lambdas are **anonymous** methods that can take parameters and return values.
>     
> - They are useful for **functional programming**, especially in LINQ queries, delegates, and event handling.
>     
> - Lambda syntax is concise, making code more readable.
>     

---

### **9.4 Built-in `Func<>`, `Action<>`, `Predicate<>`**

> C# provides several built-in generic delegate types for commonly used patterns:

- **`Func<T>`**: Represents a method that returns a value.
    
- **`Action<T>`**: Represents a method that does not return a value (void).
    
- **`Predicate<T>`**: Represents a method that returns a `bool` value, typically used for tests or conditions.
    

#### `Func<>`:

```csharp
Func<int, int, int> add = (x, y) => x + y;
Console.WriteLine(add(5, 3));  // Output: 8
```

> **Key Points**:
> 
> - `Func<>` can have up to **16** parameters, with the last parameter being the return type.
>     
> - Use `Func<>` when you need a delegate that returns a value.
>     

#### `Action<>`:

```csharp
Action<string> greet = name => Console.WriteLine($"Hello, {name}!");
greet("John");  // Output: Hello, John!
```

> **Key Points**:
> 
> - `Action<>` can have up to **16** parameters, but does not return a value.
>     
> - Use `Action<>` when you want to execute an operation with no return.
>     

#### `Predicate<>`:

```csharp
Predicate<int> isEven = x => x % 2 == 0;
Console.WriteLine(isEven(4));  // Output: True
Console.WriteLine(isEven(5));  // Output: False
```

> **Key Points**:
> 
> - `Predicate<>` is a specialized version of `Func<>` that returns a `bool`.
>     
> - Use `Predicate<>` when you need to test or match conditions.
>     

---

## **🔟 LINQ Basics**

> **Language Integrated Query (LINQ)** is a powerful feature in C# that allows you to query and manipulate collections (like arrays, lists, or databases) in a declarative manner. LINQ provides a more readable, concise, and expressive way to work with data.

### **10.1 Query Syntax vs Method Syntax**

LINQ in C# can be written using two main syntaxes: **query syntax** (which is similar to SQL) and **method syntax** (which uses LINQ extension methods). Both syntaxes achieve the same goal but have different structures.

#### **Query Syntax**

Query syntax is easier to read, especially for those familiar with SQL. It is often used for simpler queries. It’s more declarative and follows the **SELECT-FROM-WHERE** pattern.

##### Example of Query Syntax:

```csharp
var numbers = new List<int> { 1, 2, 3, 4, 5 };

var result = from num in numbers
             where num > 2
             orderby num
             select num;

Console.WriteLine(string.Join(", ", result));  // Output: 3, 4, 5
```

- **`from`**: Specifies the collection to query.
    
- **`where`**: Filters the collection based on a condition.
    
- **`orderby`**: Sorts the collection.
    
- **`select`**: Specifies the values to return.
    

**Tip**: If you're comfortable with SQL, query syntax might feel more intuitive for simple data queries, especially when you're starting with LINQ.

#### **Method Syntax**

Method syntax uses LINQ extension methods like `.Where()`, `.OrderBy()`, `.Select()`, etc. It's more flexible and can be combined with anonymous functions (lambdas).

##### Example of Method Syntax:

```csharp
var result = numbers.Where(num => num > 2)
                    .OrderBy(num => num);

Console.WriteLine(string.Join(", ", result));  // Output: 3, 4, 5
```

- **`.Where()`**: Filters the collection.
    
- **`.OrderBy()`**: Sorts the collection.
    
- **`.Select()`**: Projects the collection (can be used for transforming data).
    

**Side Note**: Method syntax is better when you need to chain multiple LINQ operators, especially for more complex queries or when working with lambda expressions.

#### **Comparison Between Query and Method Syntax**:

|Feature|Query Syntax|Method Syntax|
|---|---|---|
|**Readability**|Easier to read, especially for SQL users|More flexible but can be harder to read|
|**Complex Queries**|Can get complex with joins and groupings|More powerful, especially with lambdas|
|**Performance**|Similar performance (depending on the situation)|Equivalent performance|
|**Capabilities**|Limited compared to method syntax (cannot chain all operators)|More extensible and customizable|

**Tip**: Both syntaxes are equally powerful, so choose the one that suits your task and personal preference. If you're chaining several LINQ methods, method syntax is usually cleaner.

---

### **10.2 Filtering, Projection, Ordering**

LINQ provides several operators for **filtering**, **projecting**, and **ordering** data. These operations are fundamental to most LINQ queries.

#### **Filtering (`where`)**

The `where` clause is used to filter the data based on conditions. You can apply any boolean condition to filter the results.

##### Example:

```csharp
var numbers = new List<int> { 1, 2, 3, 4, 5 };

var filtered = numbers.Where(n => n > 2);
Console.WriteLine(string.Join(", ", filtered));  // Output: 3, 4, 5
```

- **`Where()`** is used to filter elements that meet a given condition.
    

**Side Note**: You can chain multiple `where` clauses to filter data on multiple conditions. LINQ will combine them with **AND** logic.

```csharp
var filtered = numbers.Where(n => n > 2).Where(n => n < 5);
Console.WriteLine(string.Join(", ", filtered));  // Output: 3, 4
```

#### **Projection (`select`)**

The `select` clause is used to transform or project the data into a new form. This can be done by selecting specific fields or creating new objects.

##### Example:

```csharp
var numbers = new List<int> { 1, 2, 3, 4, 5 };

var projected = numbers.Select(n => n * n);
Console.WriteLine(string.Join(", ", projected));  // Output: 1, 4, 9, 16, 25
```

- **`Select()`** is used to transform the data, such as selecting specific fields or performing operations like squaring numbers.
    

**Tip**: You can use `select` to reshape data, for instance, extracting only specific properties from complex objects or projecting into custom objects.

```csharp
var people = new List<Person>
{
    new Person { Name = "Alice", Age = 30 },
    new Person { Name = "Bob", Age = 25 },
    new Person { Name = "Charlie", Age = 35 }
};

var projected = people.Select(p => new { p.Name, p.Age });
```

#### **Ordering (`orderby`)**

The `orderby` clause sorts the data based on one or more keys. You can sort the data in ascending or descending order.

##### Example:

```csharp
var numbers = new List<int> { 5, 3, 1, 4, 2 };

var ordered = numbers.OrderBy(n => n);
Console.WriteLine(string.Join(", ", ordered));  // Output: 1, 2, 3, 4, 5
```

- **`OrderBy()`** sorts in ascending order by default. To sort in descending order, use **`OrderByDescending()`**.
    

You can also chain multiple ordering conditions:

```csharp
var people = new List<(string Name, int Age)>
{
    ("Alice", 30),
    ("Bob", 25),
    ("Charlie", 35)
};

var orderedByNameThenAge = people
    .OrderBy(p => p.Name)
    .ThenBy(p => p.Age);
```

- **`ThenBy()`**: Used to perform secondary sorting after primary ordering.
    

**Side Note**: Sorting in LINQ is **stable**, meaning it preserves the original order for items that have equal keys. This can be helpful when you want to sort by one property, then another.

---

### **10.3 Deferred vs Immediate Execution**

LINQ queries can be either **deferred execution** or **immediate execution**. Understanding how these work is essential for efficient LINQ use and for debugging performance issues.

#### **Deferred Execution**

With **deferred execution**, the query is not executed when it is defined, but rather when the data is actually iterated over. This means the query can be modified before execution.

##### Example:

```csharp
var numbers = new List<int> { 1, 2, 3, 4, 5 };

// Deferred execution
var query = numbers.Where(n => n > 2);  // Query is not executed yet

// Query is executed when iterated over
foreach (var num in query)
{
    Console.WriteLine(num);  // Output: 3, 4, 5
}
```

- The query is evaluated only when it is **iterated over**, such as inside a `foreach` loop or when you call methods like `.ToList()`, `.ToArray()`, etc.
    

**Tip**: If the data source changes before iteration, the query will reflect those changes, which can be both an advantage and a potential source of bugs.

#### **Immediate Execution**

With **immediate execution**, the query is executed right away, and the result is stored in memory. This is typically used when you want to force the query to execute at that moment.

##### Example:

```csharp
var numbers = new List<int> { 1, 2, 3, 4, 5 };

// Immediate execution
var result = numbers.Where(n => n > 2).ToList();  // Forces execution and stores the result

foreach (var num in result)
{
    Console.WriteLine(num);  // Output: 3, 4, 5
}
```

- Using methods like **`ToList()`**, **`ToArray()`**, or **`Count()`** triggers immediate execution.
    

**Side Note**: If you're working with large datasets or want to avoid repeatedly querying the same collection, **immediate execution** can be beneficial, as it allows you to work with a materialized copy of the data.

> **Key Differences**:
> 
> - **Deferred execution** is useful for queries that may change based on the collection being modified.
>     
> - **Immediate execution** is typically used when you want to materialize the results (e.g., store in a list or array) and don't expect the data to change after execution.
>     

---

### **Key Points to Remember**:

- **Query Syntax vs Method Syntax**: Both achieve the same results, but method syntax is more flexible and commonly used with complex queries or lambda expressions.
    
- **Filtering, Projection, Ordering**: These are fundamental LINQ operations used to manipulate and extract meaningful data from collections.
    
- **Deferred vs Immediate Execution**: LINQ queries can either execute when iterated (deferred) or immediately upon calling methods like `.ToList()`, `.ToArray()`, or `.Count()`.
    

**Tip**: Always be mindful of **deferred execution** when chaining multiple operations. If your collection is modified during iteration, it could lead to unexpected results.

---
