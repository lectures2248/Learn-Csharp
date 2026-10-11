## Relational Operators and Conditional Statements

---

## 1. Decision Making in C#

**Definition:** Decision making allows a program to execute different statements depending on whether a condition is `true` or `false`.

Consider a student who needs at least 50 marks to pass:

- Marks: 65 → Pass
- Marks: 42 → Fail

The decision is based on one question: **Are the marks greater than or equal to 50?**

C# uses relational operators to answer such questions and conditional statements to act on the answers.

## 2. Relational Operators

**Definition:** Relational operators compare two values. Each comparison produces a Boolean result: `true` or `false`.

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `==` | Equal to | `10 == 10` | `true` |
| `!=` | Not equal to | `10 != 5` | `true` |
| `>` | Greater than | `80 > 50` | `true` |
| `<` | Less than | `30 < 18` | `false` |
| `>=` | Greater than or equal to | `50 >= 50` | `true` |
| `<=` | Less than or equal to | `15 <= 18` | `true` |

### Comparing Values

```csharp
int marks = 65;

Console.WriteLine(marks >= 50);  // True
Console.WriteLine(marks == 100); // False
Console.WriteLine(marks != 0);   // True
```
---

## 4. The `if` Statement


**Syntax**

```csharp
if (condition)
{
    // Executes when the condition is true
}
```

**Example — Passing Marks**

```csharp
Console.Write("Enter marks: ");
int marks = Convert.ToInt32(Console.ReadLine());

if (marks >= 50)
{
    Console.WriteLine("Passed");
}
```

If the marks are less than 50, the program does not print `Passed`.

## 5. The `if-else` Statement

**Definition:** An `if-else` statement chooses between two blocks. The `if` block runs when the condition is true; otherwise, the `else` block runs.

**Syntax**

```csharp
if (condition)
{
    // True case
}
else
{
    // False case
}
```

**Example — Movie Ticket Age Check**

A particular movie requires viewers to be at least 18 years old.

```csharp
Console.Write("Enter age: ");
int age = Convert.ToInt32(Console.ReadLine());

if (age >= 18)
{
    Console.WriteLine("Eligible to watch this movie.");
}
else
{
    Console.WriteLine("Not eligible for this movie.");
}
```

| Input | Output |
|---|---|
| `20` | Eligible to watch this movie. |
| `16` | Not eligible for this movie. |
| `18` | Eligible to watch this movie. |

The value **18** is important: `>=` includes 18, while `>` would not.

## 6. The `else if` Ladder

**Definition:** An `else if` ladder checks multiple conditions in order. The first true condition determines which block runs. If none is true, the optional `else` block runs.

**Example — Student Grade**

```csharp
Console.Write("Enter percentage: ");
double percentage = Convert.ToDouble(Console.ReadLine());

if (percentage >= 80)
{
    Console.WriteLine("Grade A");
}
else if (percentage >= 70)
{
    Console.WriteLine("Grade B");
}
else if (percentage >= 60)
{
    Console.WriteLine("Grade C");
}
else if (percentage >= 50)
{
    Console.WriteLine("Grade D");
}
else
{
    Console.WriteLine("Fail");
}
```

| Percentage | Result |
|---|---|
| `85` | Grade A |
| `73` | Grade B |
| `61` | Grade C |
| `50` | Grade D |
| `42` | Fail |

The conditions are checked from top to bottom. For `85`, the first condition is true, so the remaining conditions are skipped.

## 7. Nested `if` Statements

**Definition:** A nested `if` is an `if` statement placed inside another conditional block. It is useful when a second check is required only after the first check succeeds.

**Example — ATM Withdrawal Check**

```csharp
int correctPin = 1234;
int balance = 5000;

Console.Write("Enter PIN: ");
int enteredPin = Convert.ToInt32(Console.ReadLine());

if (enteredPin == correctPin)
{
    Console.Write("Enter withdrawal amount: ");
    int amount = Convert.ToInt32(Console.ReadLine());

    if (amount > 0)
    {
        if (amount <= balance)
        {
            balance = balance - amount;
            Console.WriteLine("Withdrawal successful.");
            Console.WriteLine("Remaining balance: Rs. " + balance);
        }
        else
        {
            Console.WriteLine("Insufficient balance.");
        }
    }
    else
    {
        Console.WriteLine("Enter an amount greater than zero.");
    }
}
else
{
    Console.WriteLine("Incorrect PIN.");
}
```

The ATM first verifies the PIN. Only then does it ask for the withdrawal amount. The amount must be positive and must not exceed the balance.

---


## Student Result and Grade System

**Scenario:** A college needs to calculate a student's total marks and percentage, then display the student's result and grade.


```csharp
Console.Write("Enter English marks: ");
double english = Convert.ToDouble(Console.ReadLine());

Console.Write("Enter Mathematics marks: ");
double mathematics = Convert.ToDouble(Console.ReadLine());

Console.Write("Enter Computer Science marks: ");
double computer = Convert.ToDouble(Console.ReadLine());

double total = english + mathematics + computer;
double percentage = total / 300 * 100;

Console.WriteLine("\n----- STUDENT RESULT -----");
Console.WriteLine("Total: " + total + " / 300");
Console.WriteLine("Percentage: " + Math.Round(percentage, 2) + "%");

if (percentage >= 80)
{
    Console.WriteLine("Grade: A");
    Console.WriteLine("Result: Pass");
}
else if (percentage >= 70)
{
    Console.WriteLine("Grade: B");
    Console.WriteLine("Result: Pass");
}
else if (percentage >= 60)
{
    Console.WriteLine("Grade: C");
    Console.WriteLine("Result: Pass");
}
else if (percentage >= 50)
{
    Console.WriteLine("Grade: D");
    Console.WriteLine("Result: Pass");
}
else
{
    Console.WriteLine("Grade: F");
    Console.WriteLine("Result: Fail");
}
```

**Output**

```text
Enter English marks: 75
Enter Mathematics marks: 80
Enter Computer Science marks: 92

----- STUDENT RESULT -----
Total: 247 / 300
Percentage: 82.33%
Grade: A
Result: Pass
```

---

## ATM Example

```csharp
int correctPin = 1234;
int balance = 8000;

Console.Write("Enter your PIN: ");
int enteredPin = Convert.ToInt32(Console.ReadLine());

if (enteredPin == correctPin)
{
    Console.Write("Enter withdrawal amount: ");
    int amount = Convert.ToInt32(Console.ReadLine());

    if (amount <= 0)
    {
        Console.WriteLine("Invalid amount.");
    }
    else if (amount > balance)
    {
        Console.WriteLine("Insufficient balance.");
    }
    else
    {
        balance = balance - amount;
        Console.WriteLine("Please collect your cash.");
        Console.WriteLine("Remaining balance: Rs. " + balance);
    }
}
else
{
    Console.WriteLine("Incorrect PIN.");
}
```

**Output**

```text
Enter your PIN: 1234
Enter withdrawal amount: 2500
Please collect your cash.
Remaining balance: Rs. 5500
```

---

## Shopping Discount Calculator

**Scenario:** A shop offers a discount based on the customer's total bill.

**Discount Policy**

| Total Bill | Discount |
|---|---:|
| Rs. 10,000 or more | 20% |
| Rs. 5,000 to below Rs. 10,000 | 10% |
| Rs. 2,000 to below Rs. 5,000 | 5% |
| Below Rs. 2,000 | 0% |

```csharp
Console.Write("Enter product price: ");
double price = Convert.ToDouble(Console.ReadLine());

Console.Write("Enter quantity: ");
int quantity = Convert.ToInt32(Console.ReadLine());

double total = price * quantity;
double discountRate;

if (total >= 10000)
{
    discountRate = 20;
}
else if (total >= 5000)
{
    discountRate = 10;
}
else if (total >= 2000)
{
    discountRate = 5;
}
else
{
    discountRate = 0;
}

double discountAmount = total * discountRate / 100;
double finalBill = total - discountAmount;

Console.WriteLine("\n----- SHOPPING RECEIPT -----");
Console.WriteLine("Original bill: Rs. " + total);
Console.WriteLine("Discount: " + discountRate + "%");
Console.WriteLine("Discount amount: Rs. " + discountAmount);
Console.WriteLine("Amount to pay: Rs. " + finalBill);
```

**output**

```text
Enter product price: 1500
Enter quantity: 4

----- SHOPPING RECEIPT -----
Original bill: Rs. 6000
Discount: 10%
Discount amount: Rs. 600
Amount to pay: Rs. 5400
```
