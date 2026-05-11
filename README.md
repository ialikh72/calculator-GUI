# Calculator GUI – README

## Project Overview

This project is a simple calculator application developed using **C# Windows Forms (WinForms)** in **Visual Studio**. The calculator performs basic arithmetic operations such as:

* Addition (+)
* Subtraction (-)
* Multiplication (*)
* Division (/)
* Clear Function

The application provides a graphical user interface (GUI) where users can enter numbers and perform calculations easily.

---

# Features

* User-friendly GUI
* Basic arithmetic operations
* Error handling for division by zero
* Clear button to reset calculator
* Real-time display updates

---

# Technologies Used

* Programming Language: C#
* Framework: .NET Framework / WinForms
* IDE: Visual Studio

---

# Project Structure

## Main Components

### Form1.cs

Contains:

* Calculator logic
* Button click events
* Evaluation methods
* Input handling

### textBox1

Used to display:

* Current input
* Calculation results
* Error messages

### Buttons

The calculator contains buttons for:

| Button Type      | Function            |
| ---------------- | ------------------- |
| Number Buttons   | Input digits        |
| Operator Buttons | +, -, *, /          |
| Equal Button     | Evaluate expression |
| Clear Button     | Reset calculator    |

---

# Working Explanation

## Number Buttons

When a number button is clicked:

```csharp
Button button = (Button)sender;
currentInput += button.Text;
textBox1.Text = currentInput;
```

The pressed number is added to the current input and displayed in the textbox.

---

## Operator Buttons

When an operator button is clicked:

```csharp
operation = button.Text;
result = double.Parse(currentInput);
currentInput = "";
operationPending = true;
```

The calculator:

1. Stores the first number
2. Stores the selected operator
3. Waits for the second number

---

## Evaluate Method

The `Evaluate()` method performs calculations.

```csharp
switch (operation)
{
    case "+":
        result += secondNumber;
        break;
}
```

It:

* Reads the second number
* Performs the selected operation
* Displays the final result

---

## Division by Zero Handling

```csharp
if (secondNumber != 0)
{
    result /= secondNumber;
}
else
{
    textBox1.Text = "Error";
}
```

This prevents the application from crashing when dividing by zero.

---

# Variables Used

| Variable         | Purpose                        |
| ---------------- | ------------------------------ |
| currentInput     | Stores current user input      |
| result           | Stores calculation result      |
| operation        | Stores selected operator       |
| operationPending | Checks if operation is waiting |

---

# How to Run the Project

1. Open Visual Studio
2. Open the project solution
3. Build the project
4. Run the application using:

```text
Ctrl + F5
```

---

# Example Calculations

| Input  | Output |
| ------ | ------ |
| 5 + 3  | 8      |
| 10 - 4 | 6      |
| 7 * 2  | 14     |
| 20 / 5 | 4      |

---

# Future Improvements

The calculator can be improved by adding:

* Decimal point support
* Percentage calculations
* Square root function
* Scientific calculator features
* Keyboard input support
* Calculation history

---

# Conclusion

This project demonstrates the implementation of a basic calculator using C# WinForms. It helps in understanding:

* Event-driven programming
* GUI development
* Arithmetic operations
* Conditional statements
* Object-oriented programming concepts

The project is suitable for beginners learning Windows Forms application development in C#.
