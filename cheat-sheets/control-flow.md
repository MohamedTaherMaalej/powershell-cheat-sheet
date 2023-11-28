# PowerShell Control Flow Cheat Sheet

## Table of Contents

1. [If Statements](#if-statements)
2. [Switch Statement](#switch-statement)
3. [For Loop](#for-loop)
4. [ForEach Loop](#foreach-loop)
5. [While Loop](#while-loop)
6. [Do-While Loop](#do-while-loop)
7. [Break and Continue](#break-and-continue)
8. [Try-Catch-Finally](#try-catch-finally)

## If Statements

```powershell
if ($condition) {
    # Code to execute if the condition is true
}
elseif ($anotherCondition) {
    # Code to execute if another condition is true
}
else {
    # Code to execute if no condition is true
}
```

## Switch Statement

```powershell
$fruit = "Apple"
switch ($fruit) {
    "Apple" { Write-Output "It's an apple." }
    "Banana" { Write-Output "It's a banana." }
    default { Write-Output "Unknown fruit." }
}
```

## For Loop

```powershell
for ($i = 1; $i -le 5; $i++) {
    Write-Output $i
}
```

## ForEach Loop

```powershell
$colors = "Red", "Green", "Blue"
foreach ($color in $colors) {
    Write-Output $color
}
```

## While Loop

```powershell
$counter = 1
while ($counter -le 5) {
    Write-Output $counter
    $counter++
}
```

## Do-While Loop

```powershell
$counter = 1
do {
    Write-Output $counter
    $counter++
} while ($counter -le 5)
```

## Break and Continue

```powershell
foreach ($number in 1..10) {
    if ($number -eq 5) {
        Write-Output "Breaking loop at 5."
        break
    }
    elseif ($number -eq 3) {
        Write-Output "Skipping 3."
        continue
    }
    Write-Output $number
}
```

## Try-Catch-Finally

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
