# PowerShell Scripting Fundamentals Cheat Sheet

## Table of Contents

1. [Scripts and Functions](#scripts-and-functions)
2. [Script Structure](#script-structure)
3. [Parameters](#parameters)
4. [Variables in Scripts](#variables-in-scripts)
5. [Error Handling](#error-handling)
6. [Logging](#logging)
7. [Conditional Statements](#conditional-statements)
8. [Loops](#loops)
9. [Functions](#functions)
10. [Modules](#modules)

## Scripts and Functions

PowerShell scripts are collections of commands saved in a .ps1 file. Functions allow you to organize and reuse code.

```powershell
# Example script
param (
    [string]$name
)

Write-Output "Hello, $name!"

# Example function
function SayHello {
    param (
        [string]$name
    )
    Write-Output "Hello, $name!"
}
```

## Script Structure

- Scripts start with the `param` block for defining parameters.
- Main script logic follows the parameter block.

## Parameters

```powershell
param (
    [string]$param1,
    [int]$param2 = 42
)
```

- Parameters are defined using the `param` keyword.
- You can set default values for parameters.

## Variables in Scripts

```powershell
$scriptVariable = "Script Variable"

function ExampleFunction {
    $functionVariable = "Function Variable"
}
```

- Variables defined in a script are available globally.
- Variables inside functions are local to the function.

## Error Handling

```powershell
try {
    # Code that might throw an error
}
catch {
    # Code to handle the error
}
finally {
    # Code that always runs, whether an error occurred or not
}
```

## Logging

```powershell
Write-Host "This is a message"
Write-Output "This is an output"
Write-Warning "This is a warning"
Write-Error "This is an error"
```

- Use `Write-Host` for basic console output.
- `Write-Output` sends output to the pipeline.
- `Write-Warning` and `Write-Error` for specific message types.

## Conditional Statements

```powershell
if ($condition) {
    # Code to execute if condition is true
}
elseif ($anotherCondition) {
    # Code to execute if another condition is true
}
else {
    # Code to execute if no condition is true
}
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

## Modules

```powershell
# Save functions in a .psm1 file
# Import the module using Import-Module
Import-Module "Path\To\Your\Module.psm1"

# Call functions from the module
FunctionFromModule -param1 "Value"
```

- Modules allow you to organize functions and share them across scripts.
- Save functions in a .psm1 file and import the module using `Import-Module`.
