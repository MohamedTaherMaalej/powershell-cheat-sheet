# PowerShell Regular Expressions Cheat Sheet

## Table of Contents

1. [Introduction to Regular Expressions](#introduction-to-regular-expressions)
2. [Regex Basics](#regex-basics)
3. [Anchors](#anchors)
4. [Character Classes](#character-classes)
5. [Quantifiers](#quantifiers)
6. [Grouping and Capturing](#grouping-and-capturing)
7. [Alternation](#alternation)
8. [Escape Characters](#escape-characters)
9. [Lookahead and Lookbehind](#lookahead-and-lookbehind)
10. [PowerShell Commands with Regex](#powershell-commands-with-regex)

## Introduction to Regular Expressions

- Regular expressions (regex or regexp) are patterns used for matching character combinations in strings.
- They are widely used for text parsing, search, and validation.

## Regex Basics

- `.`: Matches any character except a newline.
- `^`: Anchors the regex at the start of the string.
- `$`: Anchors the regex at the end of the string.

## Anchors

- `^`: Matches the start of a line.
- `$`: Matches the end of a line.
- `\b`: Matches a word boundary.

## Character Classes

- `[abc]`: Matches any of the characters a, b, or c.
- `[^abc]`: Matches any character except a, b, or c.
- `[a-z]`: Matches any lowercase letter.
- `[A-Z]`: Matches any uppercase letter.
- `[0-9]`: Matches any digit.

## Quantifiers

- `*`: Matches 0 or more occurrences.
- `+`: Matches 1 or more occurrences.
- `?`: Matches 0 or 1 occurrence.
- `{n}`: Matches exactly n occurrences.
- `{n,}`: Matches n or more occurrences.
- `{n,m}`: Matches between n and m occurrences.

## Grouping and Capturing

- `()`: Groups expressions and captures the matched text.

```powershell
# Example: Extracting a date from a string
$inputString -match '(\d{4}-\d{2}-\d{2})'
$matchedDate = $matches[1]
```

## Alternation

- `|`: Acts like a logical OR.

```powershell
# Example: Matching multiple words
$pattern = 'apple|orange|banana'
$inputString -match $pattern
```

## Escape Characters

- `\`: Escapes a special character, allowing it to be treated as a literal.

```powershell
# Example: Matching a literal dot
$pattern = 'file\.txt'
$inputString -match $pattern
```

## Lookahead and Lookbehind

- `(?=...)`: Positive lookahead assertion.
- `(?<=...)`: Positive lookbehind assertion.
- `(?!...)`: Negative lookahead assertion.
- `(?<!...)`: Negative lookbehind assertion.

```powershell
# Example: Matching a word preceded by "prefix"
$pattern = '(?<=prefix)\w+'
$inputString -match $pattern
```

## PowerShell Commands with Regex

- `Select-String`: Searches for text using regex patterns.
- `-match` operator: Matches a string against a regex pattern.
- `-replace` operator: Replaces matches in a string with specified text.

```powershell
# Example: Using Select-String
Get-Content "file.txt" | Select-String -Pattern '\d{3}-\d{2}-\d{4}'

# Example: Using -match operator
"123-45-6789" -match '\d{3}-\d{2}-\d{4}'

# Example: Using -replace operator
"Hello, world!" -replace 'world', 'regex'
```

