
## 1. What are C# and .NET?

### C#
C# is an object-oriented programming language used to build different kinds of applications.

Examples:
- Console applications
- Desktop applications
- Web applications
- Services
- Other .NET-based applications

### .NET
.NET is the development platform on which C# applications can run.

Think of it like this:

```text
C# Code
   ↓
.NET
   ↓
Application Runs
```

.NET provides:
- Runtime for executing applications
- Reusable libraries
- Memory management
- Support for multiple .NET languages
- Tools for building different types of applications

---

## 2. Why do we use .NET?

Instead of developers handling everything manually, .NET provides a common environment.

Important benefits:

- Reusable classes and libraries
- Automatic memory management
- Common rules for .NET languages
- Support for different application types
- Cross-language integration

You do **not** need to memorize every .NET version.

Just remember:

```text
.NET Framework → older Windows-focused platform
.NET 5 / 6 / 7 → newer unified .NET platform
```

---

## 3. Important Components of .NET

These names sound difficult, but the idea is simple.

### CIL — Common Intermediate Language

When C# code is compiled, it is first converted into an intermediate form called **CIL**.

```text
C# Code
   ↓
Compiler
   ↓
CIL
```

### CLR — Common Language Runtime

CLR is the execution engine of .NET.

It manages things such as:
- Program execution
- Memory management
- Type safety
- Exception handling

Simple flow:

```text
C# Code
   ↓
CIL
   ↓
CLR
   ↓
Machine Code
   ↓
Program Runs
```

### FCL — Framework Class Library

FCL provides reusable classes.

For example, instead of creating your own console system, C# already gives us:

```csharp
Console.WriteLine("Hello");
```

### CTS — Common Type System

CTS defines common data types used by .NET languages.

### CLS — Common Language Specification

CLS provides rules that .NET languages follow so they can work together.

### Other .NET Technologies

You will also see names such as:

- ASP.NET — Web applications
- ADO.NET — Database interaction
- WPF — Windows desktop UI
- LINQ — Querying data

For this class, just understand their purpose. No need to memorize every detail.

---

## 4. Visual Studio

Visual Studio is an **IDE — Integrated Development Environment**.

An IDE gives us one place to:

- Write code
- Build the project
- Run the program
- Find errors
- Debug applications
- Manage project files

Important parts of Visual Studio:

- **Code Editor** — where we write code
- **Solution Explorer** — shows project files
- **Error List** — shows errors
- **Output Window** — shows build/output information
- **Properties Window** — displays properties of selected items
- **Toolbox** — provides controls for supported UI projects

---


# PRACTICAL 1 — Create Your First C# Program

Create a **Console Application** in Visual Studio.

Write:

```csharp
Console.WriteLine("Hello, World!");
```

Output:

```text
Hello, World!
```

### `Console.WriteLine()`

`Console.WriteLine()` displays output and moves the cursor to the next line.

Example:

```csharp
Console.WriteLine("Hello");
Console.WriteLine("Mujtaba");
```

Output:

```text
Hello
Mujtaba
```

### `Console.Write()`

`Console.Write()` displays output but keeps the cursor on the same line.

```csharp
Console.Write("Hello ");
Console.Write("Mujtaba");
```

Output:

```text
Hello Mujtaba
```

---

# 5. Variables

A variable stores data that may be used or changed while the program runs.

Syntax:

```csharp
dataType variableName = value;
```

Example:

```csharp
string name = "Ali";
int age = 20;
double salary = 45000.50;
bool isStudent = true;
```

Think of a variable as a labelled box:

```text
age
┌─────────┐
│   20    │
└─────────┘
```

The **data type** decides what kind of value can be stored in that box.

---

## 6. Common Data Types

You do not need to memorize every numeric range in the first class.

Focus on these:

| Data Type | Used For | Example |
|---|---|---|
| `int` | Whole numbers | `25` |
| `float` | Decimal numbers | `4.5f` |
| `double` | Decimal numbers | `99.75` |
| `decimal` | High-precision decimal values | `1500.50m` |
| `char` | Single character | `'A'` |
| `string` | Text | `"Ali"` |
| `bool` | True/False | `true` |

Example:

```csharp
int semester = 2;
string studentName = "Ali";
char grade = 'A';
bool isPresent = true;
```

---

## 7. Value Types and Reference Types

C# data types are broadly divided into two categories.

### Value Types

They store their value directly.

Examples:

```text
int
float
double
char
bool
```

### Reference Types

They work with references to objects.

Examples from the course:

```text
object
string
class
delegate
interface
array
```

For now, remember only the difference in category. We will understand memory/reference behavior more deeply when we study classes and objects.

---

## 8. Variable Naming Rules

Valid:

```csharp
int age;
string studentName;
string _name;
int emp_id;
```

Invalid:

```csharp
int 2age;
int student-name;
int class;
```

Why?

- Variable names cannot start with a number.
- Special characters such as `-` are not allowed in normal identifiers.
- C# keywords cannot normally be used as variable names.

C# is also **case-sensitive**:

```csharp
int age = 20;
int Age = 25;
```

`age` and `Age` are treated as different names.

---

# User Input

To take input from the user, use:

```csharp
Console.ReadLine();
```

Example:

```csharp
Console.Write("Enter your name: ");
string name = Console.ReadLine();

Console.WriteLine("Welcome " + name);
```

Possible output:

```text
Enter your name: Ali
Welcome Ali
```

---

# 9. Converting User Input

`Console.ReadLine()` reads input as text.

So if the user enters an age and we need an integer, we convert it.

```csharp
Console.Write("Enter your age: ");
int age = Convert.ToInt32(Console.ReadLine());
```

For decimal values:

```csharp
Console.Write("Enter your salary: ");
double salary = Convert.ToDouble(Console.ReadLine());
```

Complete example:

```csharp
Console.Write("Enter your name: ");
string name = Console.ReadLine();

Console.Write("Enter your age: ");
int age = Convert.ToInt32(Console.ReadLine());

Console.Write("Enter your salary: ");
double salary = Convert.ToDouble(Console.ReadLine());

Console.WriteLine("Name: {0}, Age: {1}, Salary: {2}", name, age, salary);
```

---

## 10. Type Conversion — Simple Idea

Sometimes one data type needs to be converted into another.

### Implicit Conversion

The compiler performs the conversion automatically when it is safe.

```csharp
int number = 50;
double result = number;
```

### Explicit Conversion

We perform the conversion ourselves when required.

One common approach in beginner console programs is the `Convert` class:

```csharp
string input = "25";
int age = Convert.ToInt32(input);
```

---

# Student Introduction Program

Create a program that asks for:

- Name
- Semester
- Batch code

Then display a proper introduction.

Example:

```csharp
Console.Write("Enter your name: ");
string name = Console.ReadLine();

Console.Write("Enter your semester: ");
int semester = Convert.ToInt32(Console.ReadLine());

Console.Write("Enter your batch code: ");
string batch = Console.ReadLine();

Console.WriteLine();
Console.WriteLine("Student Information");
Console.WriteLine("Name: " + name);
Console.WriteLine("Semester: " + semester);
Console.WriteLine("Batch: " + batch);
```

---

# 11. Escape Sequences

Escape sequences help format text.

### `\n` — New Line

```csharp
Console.WriteLine("Hello\nAli");
```

Output:

```text
Hello
Ali
```

### `\t` — Tab Space

```csharp
Console.WriteLine("Name\tAge");
Console.WriteLine("Ali\t20");
```

### `\"` — Double Quote

```csharp
Console.WriteLine("I study at \"Aptech\"");
```

Output:

```text
I study at "Aptech"
```

### `\'` — Single Quote

```csharp
Console.WriteLine("Batch code is \'PR2-2026\'");
```

### `\\` — Backslash

Useful for displaying paths:

```csharp
Console.WriteLine("C:\\NewFolder\\CSharp\\Task.txt");
```

Output:

```text
C:\NewFolder\CSharp\Task.txt
```

---

# Escape Sequence Challenge

Display the following using **one or more `Console.WriteLine()` statements**:

```text
My name is Ali.
I study at "Aptech Metro Star Gate".
My batch code is 'PR2-2026'.
My task is saved at:
C:\NewFolder\AliWork\CSharp\Task.txt
```

Try to use:

```text
\n
\"
\'
\\
```

---

# 12. Constants

A variable can change:

```csharp
int age = 20;
age = 21;
```

A constant cannot be changed after declaration.

```csharp
const double PI = 3.14159;
```

If you try:

```csharp
PI = 4.5;
```

the compiler will reject it.

Use constants when a value should remain fixed.

---

## 13. Literals

A literal is a fixed value written directly in the code.

```csharp
int age = 20;
string name = "Ali";
char grade = 'A';
bool active = true;
```

Here:

```text
20
"Ali"
'A'
true
```

are literals.

---

## 14. Comments

Comments are notes for programmers and are ignored during execution.

Single-line comment:

```csharp
// Store student age
int age = 20;
```

Comments make code easier to understand.

C# also supports XML documentation comments for documenting program elements. We will use those when documentation becomes necessary; they are not required for today's small programs.

---

# 15. Operators

Operators perform operations on values.

## Arithmetic Operators

| Operator | Work |
|---|---|
| `+` | Addition |
| `-` | Subtraction |
| `*` | Multiplication |
| `/` | Division |
| `%` | Remainder |

Example:

```csharp
int num1 = 10;
int num2 = 3;

Console.WriteLine(num1 + num2);
Console.WriteLine(num1 - num2);
Console.WriteLine(num1 * num2);
Console.WriteLine(num1 / num2);
Console.WriteLine(num1 % num2);
```

---

# Calculator

Take two numbers from the user and perform all arithmetic operations.

```csharp
Console.Write("Enter first number: ");
double num1 = Convert.ToDouble(Console.ReadLine());

Console.Write("Enter second number: ");
double num2 = Convert.ToDouble(Console.ReadLine());

Console.WriteLine("Result of {0} + {1} is {2}", num1, num2, num1 + num2);
Console.WriteLine("Result of {0} - {1} is {2}", num1, num2, num1 - num2);
Console.WriteLine("Result of {0} * {1} is {2}", num1, num2, num1 * num2);
Console.WriteLine("Result of {0} / {1} is {2}", num1, num2, num1 / num2);
Console.WriteLine("Result of {0} % {1} is {2}", num1, num2, num1 % num2);
```

---

## 16. Other Operator Types

You should know that C# also provides:

### Relational Operators

Used for comparison:

```text
==
!=
>
<
>=
<=
```

They return `true` or `false`.

Example:

```csharp
Console.WriteLine(10 > 5);
```

Output:

```text
True
```

### Conditional Operators

```text
&&    AND
||    OR
```

### Increment / Decrement

```csharp
number++;
number--;
```

### Assignment Operators

```text
=
+=
-=
*=
/=
%=
```

Example:

```csharp
int score = 10;
score += 5;

Console.WriteLine(score);
```

Output:

```text
15
```

### Ternary Operator

C# also provides the conditional operator:

```text
condition ? valueIfTrue : valueIfFalse
```

We will use it properly after learning conditions.

---

# 17. Statements and Expressions

A **statement** is an instruction in a program.

```csharp
int age = 20;
```

An **expression** produces/evaluates to a value.

```csharp
10 + 5
```

In:

```csharp
int total = 10 + 5;
```

`10 + 5` is an expression and the complete line is a statement.

---

## 18. Top-Level Statements

Modern C# allows simple programs without explicitly writing a `Main()` method.

That is why code such as this can work directly:

```csharp
Console.WriteLine("Hello World");
```

For beginner console applications, this keeps the code short and lets us focus on programming concepts.

---

# Age Calculator

Take the user's current age and show their age after 5 years.

```csharp
Console.Write("Enter your current age: ");
int age = Convert.ToInt32(Console.ReadLine());

int futureAge = age + 5;

Console.WriteLine("Your age after 5 years will be: {0}", futureAge);
```

---

# Rectangle Area and Perimeter

Take length and width from the user.

```csharp
Console.Write("Enter length: ");
double length = Convert.ToDouble(Console.ReadLine());

Console.Write("Enter width: ");
double width = Convert.ToDouble(Console.ReadLine());

double area = length * width;
double perimeter = 2 * (length + width);

Console.WriteLine("Area: {0}", area);
Console.WriteLine("Perimeter: {0}", perimeter);
```

This practical combines:

```text
User Input
Conversion
Variables
Arithmetic Operators
Output
```

---

# Student Marks Calculator

Take marks of three subjects and calculate total and average.

```csharp
Console.Write("Enter English marks: ");
double english = Convert.ToDouble(Console.ReadLine());

Console.Write("Enter Math marks: ");
double math = Convert.ToDouble(Console.ReadLine());

Console.Write("Enter Computer marks: ");
double computer = Convert.ToDouble(Console.ReadLine());

double total = english + math + computer;
double average = total / 3;

Console.WriteLine();
Console.WriteLine("Total Marks: {0}", total);
Console.WriteLine("Average Marks: {0}", average);
```

---

# Simple Shopping Bill

Take product name, price, and quantity from the user and calculate the total bill.

```csharp
Console.Write("Enter product name: ");
string productName = Console.ReadLine();

Console.Write("Enter product price: ");
double price = Convert.ToDouble(Console.ReadLine());

Console.Write("Enter quantity: ");
int quantity = Convert.ToInt32(Console.ReadLine());

double total = price * quantity;

Console.WriteLine();
Console.WriteLine("Product: {0}", productName);
Console.WriteLine("Price: {0}", price);
Console.WriteLine("Quantity: {0}", quantity);
Console.WriteLine("Total Bill: {0}", total);
```

---

# Salary Breakdown

Take monthly salary and calculate yearly salary.

```csharp
Console.Write("Enter monthly salary: ");
double monthlySalary = Convert.ToDouble(Console.ReadLine());

double yearlySalary = monthlySalary * 12;

Console.WriteLine("Monthly Salary: {0}", monthlySalary);
Console.WriteLine("Yearly Salary: {0}", yearlySalary);
```

Now add a fixed bonus using a constant:

```csharp
const double BONUS = 5000;

Console.Write("Enter monthly salary: ");
double salary = Convert.ToDouble(Console.ReadLine());

double finalSalary = salary + BONUS;

Console.WriteLine("Basic Salary: {0}", salary);
Console.WriteLine("Bonus: {0}", BONUS);
Console.WriteLine("Final Salary: {0}", finalSalary);
```

This example also demonstrates why constants are useful for values that should not change during program execution.

---

# Temperature Conversion

Take temperature in Celsius and convert it to Fahrenheit.

Formula:

```text
Fahrenheit = (Celsius × 9 / 5) + 32
```

Code:

```csharp
Console.Write("Enter temperature in Celsius: ");
double celsius = Convert.ToDouble(Console.ReadLine());

double fahrenheit = (celsius * 9 / 5) + 32;

Console.WriteLine("{0} Celsius = {1} Fahrenheit", celsius, fahrenheit);
```

---

# Profile Card with Formatting

Take student information and display it using escape sequences.

```csharp
Console.Write("Enter name: ");
string name = Console.ReadLine();

Console.Write("Enter batch: ");
string batch = Console.ReadLine();

Console.Write("Enter semester: ");
int semester = Convert.ToInt32(Console.ReadLine());

Console.WriteLine();
Console.WriteLine("----- STUDENT PROFILE -----");
Console.WriteLine("Name:\t" + name);
Console.WriteLine("Batch:\t" + batch);
Console.WriteLine("Semester:\t" + semester);
Console.WriteLine("Institute:\t\"Aptech\"");
Console.WriteLine("Task Path:\tC:\\CSharp\\Tasks\\" + name);
```

This practical combines several topics from the lecture in one small program:

```text
Variables
Data Types
Console.ReadLine()
Convert Methods
Escape Sequences
String Output
```

---



---
