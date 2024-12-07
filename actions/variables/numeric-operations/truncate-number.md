# Truncate Number

## Description
Get the integral or fractional digits of a numeric value, or round up the value to a specified number of decimal places.

## Syntax
```
Variables.TruncateNumber.GetIntegerPart Number: `[number]` Result=> TruncatedValue
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Number to truncate | Yes | Numeric value | - | Number to truncate/round up |
| Operation | Yes | Get integer part, Get decimal part, Round number | Get integer part | Operation to perform |
| Decimal places | No | Numeric value | 3 | Number of decimal places for rounding |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| TruncatedValue | Numeric value | The truncated or rounded number |

## Exceptions
This action doesn't include any exceptions.