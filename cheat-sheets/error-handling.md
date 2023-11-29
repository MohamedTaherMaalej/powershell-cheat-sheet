# PowerShell Error Handling Cheat Sheet

## Table of Contents

1. [Try-Catch-Finally](#try-catch-finally)
2. [Throwing Custom Errors](#throwing-custom-errors)
3. [ErrorActionPreference](#erroractionpreference)
4. [ErrorVariable](#errorvariable)
5. [SilentlyContinue](#silentlycontinue)
6. [$Error](#error-variable)
7. [$LASTEXITCODE](#lastexitcode)

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

## Throwing Custom Errors

```powershell
function ExampleFunction {
    try {
        # Code that might throw an error
    }
    catch {
        throw "Custom error message: $_"
    }
}
```

## ErrorActionPreference

```powershell
$ErrorActionPreference = "Stop"
# or
$ErrorActionPreference = "Continue"
# or
$ErrorActionPreference = "SilentlyContinue"
```

- Controls how PowerShell responds to errors.
- `"Stop"` stops execution on the first error.
- `"Continue"` continues execution after displaying an error.
- `"SilentlyContinue"` continues execution without displaying errors.

## ErrorVariable

```powershell
$ErrorVariable = "MyErrors"
```

- Stores errors in a variable for later analysis.

## SilentlyContinue

```powershell
# Suppresses error messages
Get-Item "NonexistentFile.txt" -ErrorAction SilentlyContinue
```

## $Error Variable

```powershell
# Access the most recent error
$error[0]
```

- `$Error` is an array that stores all errors that occurred during the session.
- Index `0` refers to the most recent error.

## $LASTEXITCODE

```powershell
# Access the exit code of the last executed process
$LASTEXITCODE
```

- Contains the exit code of the last external process that was run.


