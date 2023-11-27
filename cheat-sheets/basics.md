# PowerShell Basics Cheat Sheet

## Table of Contents

1. [Introduction](#introduction)
2. [Getting Help](#getting-help)
3. [Cmdlets](#cmdlets)
4. [Variables](#variables)
5. [Arrays](#arrays)
6. [Strings](#strings)
7. [Loops](#loops)
8. [Conditional Statements](#conditional-statements)
9. [Functions](#functions)
10. [Pipelines](#pipelines)
11. [Comments](#comments)

## Introduction

PowerShell is a task automation framework and scripting language designed for system administration. It provides a powerful command-line interface for managing Windows systems.

## Getting Help

- `Get-Help <cmdlet>`: Get help for a specific cmdlet.
- `Get-Command <keyword>`: List all commands containing a keyword.
- `Get-Help about_<topic>`: Access help about specific topics.

## Cmdlets

- `Get-Command`: List all available commands.
- `Get-Process`: Get information about running processes.
- `Get-Service`: Retrieve information about services.
- `Get-EventLog`: Access Windows event logs.

## Variables

```powershell
$variableName = "Hello, PowerShell!"
```

## Arrays

```powershell
$array = @(1, 2, 3, 4, 5)
```

## Strings

```powershell
$greeting = "Hello"
$name = "John"
$welcomeMessage = "$greeting, $name!"
```

## Loops

### For Loop

```powershell
for ($i=1; $i -le 5; $i++) {
    Write-Output $i
}
```

### ForEach Loop

```powershell
$colors = "Red", "Green", "Blue"
foreach ($color in $colors) {
    Write-Output $color
}
```

## Conditional Statements

### If Statement

```powershell
if ($condition) {
    # Code to execute if condition is true
} elseif ($anotherCondition) {
    # Code to execute if another condition is true
} else {
    # Code to execute if no condition is true
}
```

### Switch Statement

```powershell
$fruit = "Apple"
switch ($fruit) {
    "Apple" { Write-Output "It's an apple." }
    "Banana" { Write-Output "It's a banana." }
    default { Write-Output "Unknown fruit." }
}
```

## Functions

```powershell
function SayHello {
    param (
        [string]$name
    )
    Write-Output "Hello, $name!"
}

SayHello -name "Alice"
```

## Pipelines

```powershell
Get-Process | Where-Object { $_.WorkingSet -gt 100MB } | Stop-Process
```

## Comments

```powershell
# This is a single-line comment

<#
This is a
multi-line
comment block
#>
```

