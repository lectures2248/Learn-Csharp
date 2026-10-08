

## 1. Introduction to .NET Framework and .NET 

### What is .NET?

.NET is a development platform that provides a runtime and reusable libraries for building applications. C# is one of the programming languages used with .NET.

**Common uses:** Console applications, desktop applications, web applications, and services.

```text
C# Source Code
      ↓
.NET Tools and Runtime
      ↓
Running Application
```

.NET provides reusable classes, memory management, a runtime to execute applications, and support for multiple .NET languages.

### .NET Framework vs modern .NET

| .NET Framework | Modern .NET |
|---|---|
| Older .NET implementation, primarily for Windows | Current cross-platform .NET implementation |
| Common in existing Windows applications | Used for modern console, web, cloud, and other applications |

**Class discussion:** If you write a billing application, what should you focus on: implementing all memory management yourself or writing the billing features? Explain how .NET helps with common infrastructure.

---

## 2. CLR, CTS, CLS and Managed Code 

### CLR — Common Language Runtime

The CLR is the runtime that executes managed .NET code. It provides services such as:

- Execution of managed code
- Automatic memory management (garbage collection)
- Exception handling
- Type safety checks

**Simple example:** When an application creates objects, the runtime helps manage their allocated memory.

### CTS — Common Type System

The CTS defines how types are represented and used within .NET, helping different .NET languages share data types.

```csharp
int age = 20;
string name = "Ali";
bool isStudent = true;
```

These C# types participate in the .NET type system.

### CLS — Common Language Specification

The CLS is a set of language-interoperability rules. A library that exposes CLS-compliant public members can be used more easily from different .NET languages.

**Remember the difference:** CTS defines the type system; CLS describes a common subset of rules for language interoperability.

### Managed Code

Code executed under the .NET runtime's management is called **managed code**. The CLR provides runtime services to that code, including garbage collection and exception handling.

**Quick check:** Which component executes managed code: CLR, CTS, or CLS?

---

## 3. How C# Code Executes — Compilation, IL and JIT 

When a typical C# program is built and executed, the process is:

```text
C# Source Code (.cs)
         ↓
    C# Compiler
         ↓
Intermediate Language (IL / CIL)
         ↓
.NET Runtime + JIT Compiler
         ↓
Native Machine Code
         ↓
       Output
```

- **Compilation:** The C# compiler converts source code into Intermediate Language (IL), stored in an assembly.
- **IL / CIL:** An intermediate instruction format, not the original C# source code and not yet the final machine instructions in a typical JIT execution path.
- **JIT (Just-in-Time):** Compiles methods from IL into native machine code when needed during execution.

**Example:** `Console.WriteLine("Hello");` is C# source. The compiler processes it into IL, and runtime execution ultimately uses machine instructions.

**Question:** Why do we distinguish the C# compiler from the JIT compiler?

---

## 4. Introduction to C# and Its Features 

C# is a modern, strongly typed, object-oriented programming language used to build applications with .NET.

### Main features

- **Object-oriented:** Supports classes, objects, inheritance and other OOP concepts.
- **Strongly typed:** Values and variables have defined types checked by the language and runtime.
- **Automatic memory management:** Managed memory is handled with garbage collection.
- **Rich libraries:** .NET provides reusable APIs.
- **Multiple application types:** Console, desktop, web, and services.

### Where can C# be used?

| Application | Example |
|---|---|
| Console | Simple student information program |
| Desktop | School fee management system |
| Web | Online admission portal |
| Service | Background notification service |

**Class question:** Which type of application would you build for a library counter that only needs to accept and display basic information?

---

## 5. First Console Application, `Main()` and `Console.WriteLine()`

### Visual Studio

Visual Studio is an IDE (Integrated Development Environment) used to write, build, run and debug applications. The **Code Editor** holds your code; **Solution Explorer** shows project files; **Error List** helps locate errors.

Create a **C# Console App** project in Visual Studio.

### First program (modern C# top-level statements)

```csharp
Console.WriteLine("Hello, World!");
```

**Output:**

```text
Hello, World!
```

Modern C# console templates commonly use **top-level statements**; this means you may not see an explicitly written `Main()` method.

### The same idea with an explicit `Main()` method

```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Hello, World!");
    }
}
```

- `using System;` makes types in the `System` namespace available without writing their fully qualified names.
- `class Program` declares a class.
- `Main()` is the application's entry point in this explicit form.
- `Console.WriteLine()` displays text and ends the line.

### `Console.WriteLine()` vs `Console.Write()`

```csharp
Console.WriteLine("Hello");
Console.WriteLine("Ali");
```

```text
Hello
Ali
```

```csharp
Console.Write("Hello ");
Console.Write("Ali");
```

```text
Hello Ali
```

**Mini challenge:** Display your name, course and institute on three separate lines. Then display your first and last name on the same line using `Console.Write()`.

---

## 6. Practical — Student Introduction Card

**Goal:** Display a formatted student card with text already written in the program. We will take keyboard input later in this lecture.

```csharp
Console.WriteLine("============================");
Console.WriteLine("    STUDENT INTRODUCTION");
Console.WriteLine("============================");
Console.WriteLine("Name: Ali");
Console.WriteLine("Course: C# Programming");
Console.WriteLine("Institute: Aptech");
Console.WriteLine("Batch: PR2-2026");
Console.WriteLine("============================");
```

**Expected output:**

```text
============================
    STUDENT INTRODUCTION
============================
Name: Ali
Course: C# Programming
Institute: Aptech
Batch: PR2-2026
============================
```

**Student challenge:** Replace the sample values with your own details, add a `Semester` line, and make a card with your own heading.

---

## 7. Variables and Data Types 

A **variable** stores data that a program can use or change.

```csharp
string name = "Ali";
int age = 20;
double salary = 45000.50;
bool isStudent = true;
```

**Basic syntax:**

```csharp
dataType variableName = value;
```

### Common C# data types

| Type | Purpose | Example |
|---|---|---|
| `int` | Whole numbers | `25` |
| `float` | Decimal numbers | `4.5f` |
| `double` | Decimal numbers | `99.75` |
| `decimal` | Decimal values (often useful for money) | `1500.50m` |
| `char` | Single character | `'A'` |
| `string` | Text | `"Ali"` |
| `bool` | True / false | `true` |

```csharp
string studentName = "Ali";
int semester = 2;
char grade = 'A';
bool isPresent = true;

Console.WriteLine(studentName);
Console.WriteLine(semester);
Console.WriteLine(grade);
Console.WriteLine(isPresent);
```

### Variable naming

Valid names: `studentName`, `age`, `_name`, `batchCode`  
Invalid names: `2age`, `student-name`, `class` (a reserved keyword unless escaped)

C# is case-sensitive: `age` and `Age` are different identifiers.

**Practice:** Declare variables for a student's name, semester, attendance status and grade. Print their values.

---

## 8. Type Conversion

Type conversion means converting a value from one type into another.

### Implicit conversion

A compatible conversion may happen automatically:

```csharp
int number = 50;
double result = number;
Console.WriteLine(result);
```

### Explicit cast

You specify a conversion directly:

```csharp
double price = 99.75;
int wholePrice = (int)price;
Console.WriteLine(wholePrice); // 99
```

A cast from `double` to `int` drops the fractional part; it does not round.

### Converting text to numbers with `Convert`

```csharp
string input = "25";
int age = Convert.ToInt32(input);
Console.WriteLine(age + 5); // 30
```

Other examples: `Convert.ToDouble("12.5")` and `Convert.ToInt32("20")` (numeric text must be valid for the conversion and culture settings).

**Predict the output:** What will `(int) 9.8` display?

---

## 9. `Console.ReadLine()` and `Console.WriteLine()` 
`Console.ReadLine()` reads a line of text entered by the user. `Console.WriteLine()` displays output and moves to the next line; `Console.Write()` displays output without automatically starting a new line.

### Example 1 — Welcome message

```csharp
Console.Write("Enter your name: ");
string? name = Console.ReadLine();

Console.WriteLine("Welcome " + name);
```

**Sample run:**

```text
Enter your name: Ali
Welcome Ali
```

`ReadLine()` returns text (or `null` when no input is available), which is why `string?` is used here.

### Example 2 — Age after five years

```csharp
Console.Write("Enter your age: ");
int age = Convert.ToInt32(Console.ReadLine());

int futureAge = age + 5;
Console.WriteLine("Your age after 5 years: " + futureAge);
```

**Sample run:**

```text
Enter your age: 20
Your age after 5 years: 25
```

This beginner example assumes the user enters a valid whole number; invalid input can cause a conversion error.

### Example 3 — Interactive student card

```csharp
Console.Write("Enter your name: ");
string? name = Console.ReadLine();

Console.Write("Enter your semester: ");
int semester = Convert.ToInt32(Console.ReadLine());

Console.Write("Enter your batch code: ");
string? batch = Console.ReadLine();

Console.WriteLine();
Console.WriteLine("----- STUDENT INFORMATION -----");
Console.WriteLine("Name: " + name);
Console.WriteLine("Semester: " + semester);
Console.WriteLine("Batch: " + batch);
```

