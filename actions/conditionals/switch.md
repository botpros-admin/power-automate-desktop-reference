# Switch

## Description
Dispatches execution to different parts of the switch body based on the value of the expression.

## Syntax
```
SWITCH `[value]`
    [cases]
END
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Value to check | Yes | * | - | Enter a value name, text, or number to compare with the following cases |

## Output Variables
This action doesn't produce any variables.

## Exceptions
This action doesn't include any exceptions.

## Example Usage

```
SWITCH ButtonPressed
    CASE = $'''Yes'''
        [actions]
    CASE = $'''No'''
        [actions]
    CASE < 44
        [actions]
    DEFAULT
        [actions]
END
```

## Syntax Notes
1. Each CASE starts at new line with proper indentation
2. String values use $''' ''' syntax
3. Numeric comparisons can use any valid operator
4. DEFAULT case is optional but recommended
5. END statement is required

## Common Patterns

### String Comparison
```
SWITCH UserInput
    CASE = $'''Option1'''
    CASE = $'''Option2'''
    DEFAULT
END
```

### Numeric Comparison
```
SWITCH Score
    CASE > 90
    CASE > 80
    CASE > 70
    DEFAULT
END
```

### Mixed Types
```
SWITCH Status
    CASE = $'''Active'''
    CASE = 1
    CASE = True
    DEFAULT
END
```