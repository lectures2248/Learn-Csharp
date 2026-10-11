## Logical Operators, Switch Statements & Ternary Operator


---

## 1. Logical Operators

**Definition:** Logical operators combine or reverse Boolean expressions. The result is `true` or `false`.

| Operator | Name | Meaning | Real-world example |
|---|---|---|---|
| `&&` | AND | Both conditions must be true | Age is 18 or above **and** an ID is available |
| `\|\|` | OR | At least one condition must be true | Customer is a student **or** a senior citizen |
| `!` | NOT | Reverses a Boolean value | An account is **not** blocked |

### Example: Account Access

```csharp
bool correctPin = true;
bool isBlocked = false;

if (correctPin && !isBlocked)
{
    Console.WriteLine("Access Granted");
}
else
{
    Console.WriteLine("Access Denied");
}
```

**Output**

```text
Access Granted
```

Change `correctPin` to `false` or `isBlocked` to `true` and observe the result.

### Example1 — Login Validation

**Scenario:** A training portal accepts a login only when both username and password match.

```csharp
Console.Write("Enter username: ");
string username = Console.ReadLine() ?? "";

Console.Write("Enter password: ");
string password = Console.ReadLine() ?? "";

if (username == "student" && password == "1234")
{
    Console.WriteLine("Login Successful");
}
else
{
    Console.WriteLine("Invalid Username or Password");
}
```

---

## 2. Switch Statements

**Definition:** A `switch` statement executes a matching block of code based on the value of an expression. It is useful for fixed choices such as menu options.

- `switch` checks the selected value.
- `case` defines a possible match.
- `break` exits the switch statement.
- `default` handles unmatched choices.

### Restaurant Menu: `if-else` vs `switch`

**Scenario:** A customer selects a food item by entering a menu number.

**Version A — Using `if-else`**

```csharp
Console.Write("Choose an item (1-3): ");
int choice = Convert.ToInt32(Console.ReadLine());

if (choice == 1)
{
    Console.WriteLine("Burger Selected");
}
else if (choice == 2)
{
    Console.WriteLine("Pizza Selected");
}
else if (choice == 3)
{
    Console.WriteLine("Pasta Selected");
}
else
{
    Console.WriteLine("Invalid Choice");
}
```

**Version B — Using `switch`**

```csharp
Console.Write("Choose an item (1-3): ");
int choice = Convert.ToInt32(Console.ReadLine());

switch (choice)
{
    case 1:
        Console.WriteLine("Burger Selected");
        break;

    case 2:
        Console.WriteLine("Pizza Selected");
        break;

    case 3:
        Console.WriteLine("Pasta Selected");
        break;

    default:
        Console.WriteLine("Invalid Choice");
        break;
}
```

**output**

```text
Choose an item (1-3): 2
Pizza Selected
```

### When to Use `if-else` and `switch`

| `if-else` | `switch` |
|---|---|
| Checks general Boolean conditions | Selects among matching cases |
| Natural for ranges, such as `marks >= 50` | Natural for fixed menu choices, such as `1`, `2`, `3` |
| Can combine conditions with `&&` and `\|\|` | Keeps many straightforward choices organized |


---

## 3. Ternary Operator (`?:`)

**Definition:** The ternary operator evaluates a Boolean condition and returns one of two expressions.

**Syntax**

```csharp
condition ? valueIfTrue : valueIfFalse
```

### Practical 3 — Student Pass/Fail

**Scenario:** Display `Pass` when a student's marks are at least 50; otherwise display `Fail`.

**Using `if-else`**

```csharp
Console.Write("Enter marks: ");
int marks = Convert.ToInt32(Console.ReadLine());

string result;

if (marks >= 50)
{
    result = "Pass";
}
else
{
    result = "Fail";
}

Console.WriteLine("Result: " + result);
```

**Using the ternary operator**

```csharp
Console.Write("Enter marks: ");
int marks = Convert.ToInt32(Console.ReadLine());

string result = marks >= 50 ? "Pass" : "Fail";

Console.WriteLine("Result: " + result);
```

**output**

```text
Enter marks: 75
Result: Pass
```

Use a ternary expression when choosing between two simple values. Use `if-else` when several statements or more complex decisions are involved.

---

## Assigmnet — Menu-Driven Calculator

**Scenario:** A small calculator takes two numbers and lets the user choose an operation.

**Requirements**

1. Enter two numbers.
2. Display a menu: `1. Add`, `2. Subtract`, `3. Multiply`, `4. Divide`.
3. Use `switch` to perform the selected operation.
4. Display `Invalid Choice` for an unknown option.
5. Check for division by zero before dividing.
---
