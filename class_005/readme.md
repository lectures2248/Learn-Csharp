## Loops and Iteration Statements

## 1. Introduction to Loops

**Definition:** A loop repeatedly executes a block of code according to a condition.

## 2. The `for` Loop

**Definition:** A `for` loop is commonly used when the number of repetitions is known.

**Syntax:**

```csharp
for (initialization; condition; update)
{
    // Statements
}
```
- `int i = 1` starts the counter at 1.
- `i <= 5` keeps the loop running while the condition is true.
- `i++` increases the counter after each iteration.

**Example — Countdown:**

```csharp
for (int i = 5; i >= 1; i--)
{
    Console.WriteLine(i);
}
```

## 3. The `while` Loop

**Definition:** A `while` loop repeats instructions as long as its condition is true. The condition is checked before each iteration.

```csharp
int number = 1;

while (number <= 5)
{
    Console.WriteLine(number);
    number++;
}
```

**Output:** `1`, `2`, `3`, `4`, `5` (each on a new line).

The counter must change inside the loop. Otherwise, the condition could stay true indefinitely.

## 4. The `do-while` Loop

**Definition:** A `do-while` loop executes its body at least once and checks the condition afterward.

```csharp
int number = 1;

do
{
    Console.WriteLine(number);
    number++;
}
while (number <= 5);
```

**Why it matters:** A menu can appear at least once, even before the program knows whether the user wants to continue.

## 5. Difference Between `for`, `while`, and `do-while`

| `for` | `while` | `do-while` |
|---|---|---|
| Often used for a known number of repetitions | Often used when repetition depends on a condition | Often used when the task must run at least once |
| Checks condition before the body | Checks condition before the body | Checks condition after the body |
| Can run zero times | Can run zero times | Runs at least once |

All three loops can solve many of the same problems. The choice depends on which one makes the code clearest.

## 6. `break` and `continue`

**`break`** immediately exits the nearest loop.

```csharp
for (int i = 1; i <= 5; i++)
{
    if (i == 4)
    {
        break;
    }
    Console.WriteLine(i);
}
```

**Output:**

```text
1
2
3
```

**`continue`** skips the remaining code in the current iteration and moves to the next iteration.

```csharp
for (int i = 1; i <= 5; i++)
{
    if (i == 3)
    {
        continue;
    }
    Console.WriteLine(i);
}
```

**Output:**

```text
1
2
4
5
```

---

## Practical 1 — Multiplication Table Generator

**Scenario:** A student enters any number, and the program displays its multiplication table from 1 to 10.

```csharp
Console.Write("Enter a number: ");
int number = Convert.ToInt32(Console.ReadLine());

for (int i = 1; i <= 10; i++)
{
    Console.WriteLine(number + " x " + i + " = " + (number * i));
}
```

**Example input:** `5`

**Output:**

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
...
5 x 10 = 50
```
---

## Assigmnet -Simple ATM Menu

**Scenario:** A customer can check the balance, deposit money, withdraw money, or exit. The menu appears again after each transaction until Exit is selected.

```csharp
double balance = 5000;
int choice;

do
{
    Console.WriteLine("\n--- ATM MENU ---");
    Console.WriteLine("1. Check Balance");
    Console.WriteLine("2. Deposit");
    Console.WriteLine("3. Withdraw");
    Console.WriteLine("4. Exit");
    Console.Write("Enter choice: ");
    choice = Convert.ToInt32(Console.ReadLine());

    switch (choice)
    {
        case 1:
            Console.WriteLine("Balance: Rs. " + balance);
            break;

        case 2:
            Console.Write("Enter deposit amount: ");
            double deposit = Convert.ToDouble(Console.ReadLine());
            if (deposit > 0)
            {
                balance += deposit;
                Console.WriteLine("Deposit successful.");
            }
            else
            {
                Console.WriteLine("Amount must be greater than zero.");
            }
            break;

        case 3:
            Console.Write("Enter withdrawal amount: ");
            double withdrawal = Convert.ToDouble(Console.ReadLine());
            if (withdrawal > 0 && withdrawal <= balance)
            {
                balance -= withdrawal;
                Console.WriteLine("Withdrawal successful.");
            }
            else
            {
                Console.WriteLine("Invalid amount or insufficient balance.");
            }
            break;

        case 4:
            Console.WriteLine("Thank you for using the ATM.");
            break;

        default:
            Console.WriteLine("Invalid menu choice.");
            break;
    }
}
while (choice != 4);
```
