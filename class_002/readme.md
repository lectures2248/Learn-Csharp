# C# Programming — Class 02
## Data Types, Value Types, Reference Types, and Operators

---

## Data Types in C#

### Definition
A **data type** specifies the kind of data a variable can hold. Selecting an appropriate data type helps a program store and process information correctly.

### Example: Student Admission Record
A student admission system stores different kinds of information:

| Information | Suitable Type | Example |
|---|---|---|
| Student name | `string` | `"Ali"` |
| Age | `int` | `19` |
| Attendance percentage | `double` | `88.5` |
| Course fee | `decimal` | `15000.50m` |
| Grade | `char` | `'A'` |
| Admission confirmed | `bool` | `true` |

### Common C# Data Types

| Type | Description | Example |
|---|---|---|
| `int` | Whole numbers | `25` |
| `float` | Decimal numbers (single precision) | `75.5f` |
| `double` | Decimal numbers (double precision) | `88.75` |
| `decimal` | Decimal numbers well suited to financial amounts | `1250.75m` |
| `char` | One character | `'A'` |
| `string` | Text (a sequence of characters) | `"Ahmed"` |
| `bool` | `true` or `false` | `true` |

```csharp
string studentName = "Ali";
int age = 19;
double attendance = 88.5;
decimal fee = 15000.50m;
char grade = 'A';
bool isAdmitted = true;

Console.WriteLine("Student: " + studentName);
Console.WriteLine("Age: " + age);
Console.WriteLine("Attendance: " + attendance + "%");
Console.WriteLine("Fee: Rs. " + fee);
Console.WriteLine("Grade: " + grade);
Console.WriteLine("Admission Confirmed: " + isAdmitted);
```

**Key point:** A telephone number or student registration ID is often stored as `string`, even when it contains digits, because it is an identifier rather than a value used for calculations.

---

## Value Types

### Definition
A **value type** is a type whose variable directly contains its value. Assigning one value-type variable to another copies the value; changing one variable does not change the other.

Common examples: `int`, `float`, `double`, `decimal`, `char`, and `bool`.

###  Example: Separate Cash
Ali has **Rs. 1,000**. Ahmed receives his **own separate Rs. 1,000**. Ali spends Rs. 500, leaving him with Rs. 500. Ahmed still has Rs. 1,000 because his money is separate.

```csharp
int ali = 1000;
int ahmed = ali;   // Copy the value

ali = 500;

Console.WriteLine("Ali: Rs. " + ali);
Console.WriteLine("Ahmed: Rs. " + ahmed);
```

**Output**
```text
Ali: Rs. 500
Ahmed: Rs. 1000
```

**Why?** `ahmed = ali` copied the number `1000`. It did not link the two variables together.

---

## Reference Types

### Definition
A **reference type** is a type whose variable stores a reference to an object. Two reference-type variables can refer to the **same object**.

Examples include `string`, arrays . 

### Real-World Example: One Joint Bank Account
Ali and Ahmed have access to **one joint bank account** with a balance of **Rs. 1,000**. Ali deposits Rs. 500 into that account. When Ahmed checks the **same account**, its balance is **Rs. 1,500**.

The account was updated once; both people see the updated balance because they access the same account.

```text
Ali ---------\
              > ONE SHARED ACCOUNT: Rs. 1,000 → Rs. 1,500
Ahmed -------/
```
---
# Operators
**operators** are used to perform operation b/w operands.

## Arithmetic Operators

### Definition
**Arithmetic operators** perform mathematical calculations on numeric values.

| Operator | Purpose | Example | Result |
|---|---|---|---|
| `+` | Addition | `10 + 5` | `15` |
| `-` | Subtraction | `10 - 5` | `5` |
| `*` | Multiplication | `10 * 5` | `50` |
| `/` | Division | `10 / 5` | `2` |
| `%` | Remainder | `10 % 3` | `1` |

### Why Integer Division Matters
When both numbers are integers, `/` returns an integer result. The fractional portion is discarded.

```csharp
Console.WriteLine(10 / 3);     // 3
Console.WriteLine(10.0 / 3);   // 3.3333333333333335 (approximately)
```

###  Remainder Operator 
The `%` operator gives the amount left over after integer division.

```csharp
int chocolates = 17;
int students = 5;

Console.WriteLine("Each student gets: " + (chocolates / students));
Console.WriteLine("Chocolates left: " + (chocolates % students));
```

**Output**
```text
Each student gets: 3
Chocolates left: 2
```

**Remember:** `/` answers **how many each?** and `%` answers **how many remain?** when dividing whole items equally.

---

## Relational Operators

### Definition
**Relational operators** compare two values and produce a Boolean result: `true` or `false`.

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `==` | Equal to | `10 == 10` | `True` |
| `!=` | Not equal to | `10 != 5` | `True` |
| `>` | Greater than | `10 > 5` | `True` |
| `<` | Less than | `10 < 5` | `False` |
| `>=` | Greater than or equal to | `18 >= 18` | `True` |
| `<=` | Less than or equal to | `7 <= 5` | `False` |

### Example: Minimum Passing Marks
A student passes when their overall percentage is at least 50%.

```csharp
double percentage = 62.5;
bool passed = percentage >= 50;

Console.WriteLine("Passed: " + passed);  // True
```

**Important:** `=` assigns a value, while `==` checks whether two values are equal.

---


## Student Result Calculator


### Program

```csharp
Console.Write("Enter English marks: ");
double english = Convert.ToDouble(Console.ReadLine());

Console.Write("Enter Mathematics marks: ");
double mathematics = Convert.ToDouble(Console.ReadLine());

Console.Write("Enter Computer marks: ");
double computer = Convert.ToDouble(Console.ReadLine());

double total = english + mathematics + computer;
double percentage = total / 300 * 100;
bool passed = percentage >= 50;

Console.WriteLine("\n----- STUDENT RESULT -----");
Console.WriteLine("Total: " + total + " / 300");
Console.WriteLine("Percentage: " + percentage + "%");
Console.WriteLine("Passed: " + passed);
```

---

##  Shopping Bill and Budget Checker

### Program

```csharp
Console.Write("Enter product price (Rs.): ");
decimal price = Convert.ToDecimal(Console.ReadLine());

Console.Write("Enter quantity: ");
int quantity = Convert.ToInt32(Console.ReadLine());

Console.Write("Enter available budget (Rs.): ");
decimal budget = Convert.ToDecimal(Console.ReadLine());

decimal totalBill = price * quantity;
decimal balance = budget - totalBill;
bool isAffordable = budget >= totalBill;

Console.WriteLine("\n----- SHOPPING BILL -----");
Console.WriteLine("Total Bill: Rs. " + totalBill);
Console.WriteLine("Balance After Purchase: Rs. " + balance);
Console.WriteLine("Affordable: " + isAffordable);
```


##  Chocolate Distribution System

### Program

```csharp
Console.Write("Enter total chocolates: ");
int chocolates = Convert.ToInt32(Console.ReadLine());

Console.Write("Enter number of students: ");
int students = Convert.ToInt32(Console.ReadLine());

// Enter at least one student.
int eachStudentGets = chocolates / students;
int remaining = chocolates % students;
bool leftoversExist = remaining > 0;

Console.WriteLine("\n----- DISTRIBUTION -----");
Console.WriteLine("Chocolates per student: " + eachStudentGets);
Console.WriteLine("Chocolates remaining: " + remaining);
Console.WriteLine("Leftovers exist: " + leftoversExist);
```
---
