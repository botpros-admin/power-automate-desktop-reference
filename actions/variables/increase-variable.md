# Increase Variable Action

## Description
Increase the value of a numeric variable by a specific amount.

## Syntax
```
Variables.IncreaseVariable Value: `` IncrementValue: ``
```

## Parameters
- Value (Required): The numeric value to increase
- IncrementValue (Required): Amount to increase by

## Examples
```powershell
# Increase counter by 1
Variables.IncreaseVariable Value: %Counter% IncrementValue: 1

# Increase by variable amount
Variables.IncreaseVariable Value: %Score% IncrementValue: %Points%
```