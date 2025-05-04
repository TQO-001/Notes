# C# Reference Notes – Expanded Edition

## 1. Basics – Structure of a C# Program

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");
        }
    }
}
```

### Breakdown:

- `using System;`  
    Brings in the `System` namespace which contains basic classes like `Console`.
    
- `namespace HelloWorld`  
    A namespace is like a container for related classes. Helps organize code.
    
- `class Program`  
    C# is class-based. Every piece of executable code must be inside a class or struct.
    
- `static void Main(string[] args)`  
    Entry point of a C# console app.
    
    - `static` means you don’t need an instance of `Program` to call `Main`.
        
    - `void` means it doesn’t return anything.
        
    - `string[] args` allows command-line arguments.
        
- `Console.WriteLine("Hello, World!");`  
    Writes text to the console with a newline.
    

---

## 2. Data Types & Variables

### Value Types (Stored on the Stack)

```csharp
int age = 25;
double pi = 3.1415;
bool isAlive = true;
char initial = 'T';
```

These store actual values and are efficient.

|Type|Size|Default|Notes|
|---|---|---|---|
|`int`|4 bytes|`0`|Whole numbers|
|`double`|8 bytes|`0.0`|Floating point|
|`bool`|1 byte|`false`|True or false|
|`char`|2 bytes|`'\0'`|Unicode character|
|`float`|4 bytes|`0.0f`|Less precise than `double`|
|`decimal`|16 bytes|`0.0m`|High-precision decimals|

### Reference Types (Stored on the Heap)

```csharp
string name = "Thulani";
object any = 42;
```

These store a reference (pointer) to the data in memory.

|Type|Description|
|---|---|
|`string`|Sequence of Unicode characters|
|`object`|Base type for all other types|
|`dynamic`|Skips compile-time type checking|

---

## 3. Control Flow

### If / Else If / Else

```csharp
int score = 85;

if (score >= 90)
    Console.WriteLine("A");
else if (score >= 80)
    Console.WriteLine("B");
else
    Console.WriteLine("C or lower");
```

### Ternary Operator

```csharp
string result = (score >= 50) ? "Pass" : "Fail";
```

---

### Switch (Better alternative to multiple `if`)

```csharp
int day = 3;

switch (day)
{
    case 1:
        Console.WriteLine("Monday");
        break;
    case 2:
        Console.WriteLine("Tuesday");
        break;
    default:
        Console.WriteLine("Other Day");
        break;
}
```

---

## 4. Loops

### For Loop

```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```

### While Loop

```csharp
int i = 0;
while (i < 5)
{
    Console.WriteLine(i);
    i++;
}
```

### Do-While Loop (Executes at least once)

```csharp
int i = 0;
do
{
    Console.WriteLine(i);
    i++;
} while (i < 5);
```

### Foreach Loop (For collections)

```csharp
string[] names = { "Alice", "Bob", "Charlie" };

foreach (string name in names)
{
    Console.WriteLine(name);
}
```

---

## 5. Methods (Functions in C#)

```csharp
int Multiply(int a, int b)
{
    return a * b;
}
```

- Must define return type and parameter types.
    
- Use `void` for methods that return nothing.
    

### Method Overloading

Same method name, different parameters:

```csharp
int Add(int a, int b) => a + b;
double Add(double a, double b) => a + b;
```

---
## 6. Classes & Objects (OOP Basics)

C# is an object-oriented language. Everything revolves around **classes** and **objects**.

### Class Definition

```csharp
class Person
{
    // Fields
    public string Name;
    public int Age;

    // Method
    public void Greet()
    {
        Console.WriteLine($"Hi, I'm {Name} and I'm {Age} years old.");
    }
}
```

- A **class** is a blueprint for creating **objects** (instances).
    
- `public` means the field or method can be accessed from outside the class.
    
- Fields can store data, and methods define behavior.
    

### Creating and Using an Object

```csharp
var person = new Person();
person.Name = "Thulani";
person.Age = 22;
person.Greet();  // Output: Hi, I'm Thulani and I'm 22 years old.
```

---

### Constructors

A constructor initializes an object when it’s created. It’s a special method with the same name as the class.

```csharp
class Animal
{
    public string Species;

    // Constructor
    public Animal(string species)
    {
        Species = species;
    }

    public void Speak()
    {
        Console.WriteLine($"I'm a {Species}");
    }
}

var dog = new Animal("Dog");
dog.Speak();  // Output: I'm a Dog
```

- If you don’t define a constructor, C# provides a default empty one.
    
- You can overload constructors by changing parameter signatures.
    

---

### Access Modifiers

|Modifier|Meaning|
|---|---|
|`public`|Accessible from anywhere|
|`private`|Accessible only within the same class|
|`protected`|Accessible within the class and derived ones|
|`internal`|Accessible within the same assembly/project|

Default is `private` if none is specified.

---

### The `this` Keyword

Used to refer to the current instance of the class.

```csharp
public Person(string name)
{
    this.Name = name;
}
```

Clarifies that you're assigning to the field `Name`, not a local variable `name`.

---

### Object Initializer Syntax

Instead of calling a constructor and setting fields manually:

```csharp
var user = new Person { Name = "Leo", Age = 30 };
```

Cleaner and preferred when you’re setting multiple properties.

---

## 7. Properties (Encapsulation & Data Control)

Properties wrap around **fields** and give controlled access to them. Think of them as cleaner `get` and `set` methods.

### Auto-Implemented Properties

```csharp
class Book
{
    public string Title { get; set; }
}
```

This is shorthand for defining a private field and public `get`/`set` accessors.

```csharp
var book = new Book();
book.Title = "The Laughing Code";
Console.WriteLine(book.Title);
```

---

### Custom Getters and Setters

You can add logic when **reading** or **writing** a property:

```csharp
class Temperature
{
    private double _celsius;

    public double Celsius
    {
        get { return _celsius; }
        set
        {
            if (value < -273.15)
                _celsius = -273.15;  // Absolute zero
            else
                _celsius = value;
        }
    }
}
```

### Read-Only or Write-Only

```csharp
public string Name { get; private set; }  // Readable everywhere, settable only in class
```

You can also define read-only properties using **expression-bodied** syntax:

```csharp
public int Age { get; }
public int BirthYear => DateTime.Now.Year - Age;
```

---

### Init-Only Setters (Immutable After Creation) – C# 9+

```csharp
public class Car
{
    public string Model { get; init; }
}

var car = new Car { Model = "Tesla" };
// car.Model = "BMW"; ❌ This would cause a compile error
```

Useful for defining **immutable objects** after they're created.

---

### Backing Fields

Sometimes, you want to keep logic or validation behind your property.

```csharp
private int _score;

public int Score
{
    get => _score;
    set
    {
        if (value >= 0) _score = value;
    }
}
```

---

### Summary Table

|Syntax|Purpose|
|---|---|
|`{ get; set; }`|Auto-implemented|
|`{ get; private set; }`|Public read, private write|
|`{ get => expr; }`|Read-only, expression-bodied|
|`init;`|Settable only at object init|

---

Next up: **Inheritance & Polymorphism** — we’ll cover how classes relate to each other and how to override behavior properly. Ready?