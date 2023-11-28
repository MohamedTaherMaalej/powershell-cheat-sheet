# PowerShell Variables and Data Types Cheat Sheet

## Table of Contents

1. [Variables](#variables)
2. [Data Types](#data-types)
3. [String Manipulation](#string-manipulation)
4. [Numbers and Math](#numbers-and-math)
5. [Arrays](#arrays)
6. [HashTables](#hashtables)
7. [Booleans](#booleans)
8. [Null Values](#null-values)

## Variables

Variables are used to store and manage data in PowerShell.

```powershell
$variableName = "Hello, PowerShell!"
```

- Variable names are case-insensitive.
- Use descriptive names for clarity.
- Variables are created by assigning a value using the `=` operator.

## Data Types

### Strings

```powershell
$stringVariable = "This is a string."
```

### Numbers

```powershell
$intVariable = 42
$floatVariable = 3.14
```

### Arrays

```powershell
$arrayVariable = @(1, 2, 3, 4, 5)
```

### HashTables

```powershell
$hashTableVariable = @{
    Key1 = "Value1"
    Key2 = "Value2"
}
```

### Booleans

```powershell
$trueVariable = $true
$falseVariable = $false
```

### Null Values

```powershell
$nullVariable = $null
```

## String Manipulation

```powershell
$greeting = "Hello"
$name = "John"
$welcomeMessage = "$greeting, $name!"
```

- Use double-quoted strings to interpolate variables.
- Single-quoted strings are literal and don't interpolate variables.

## Numbers and Math

```powershell
$number1 = 10
$number2 = 5

$sum = $number1 + $number2
$difference = $number1 - $number2
$product = $number1 * $number2
$quotient = $number1 / $number2
```

