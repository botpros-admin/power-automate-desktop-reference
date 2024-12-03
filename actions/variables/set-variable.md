# Set Variable Action

## Description
Set the value of a new or existing variable.

## Syntax
```
SET VariableName TO Value
```

## Parameters
- VariableName: The name of the variable to set
- Value: The value to assign to the variable

## Examples
```powershell
# Set a text variable
SET UserName TO "John Doe"

# Set a numeric variable
SET Counter TO 1

# Set variable from another variable
SET NewVar TO %ExistingVar%

# Set a list variable
SET UserList TO ["John", "Jane", "Bob"]
```

## Notes
- Variable names must start with a letter or underscore
- Names are not case-sensitive
- Reserved keywords cannot be used as variable names
- Variables can hold any type of value (text, number, list, etc.)