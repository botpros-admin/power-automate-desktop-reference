# Else If

## Description
Marks the beginning of a block of actions that run if the conditions specified in the preceding 'If' statements aren't met, but the condition specified in this statement is met.

## Syntax
```
ELSE IF `[first operand]` = `[second operand]` THEN
    [actions]
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Operator | Yes | Equal to (=), Not equal to (<>), Greater than (>), Greater than or equal to (>=), Less than (<), Less than or equal to (<=), Contains, Does not contain, Is empty, Is not empty, Starts with, Does not start with, Ends with, Does not end with, Is blank, Is not blank | Equal to (=) | Choose the relationship of first operand to the second operand |
| First operand | Yes | * | - | Enter a value name defined by a previous action, text, number or expression to compare with the second operand |
| Second operand | Yes | * | - | Enter a value name produced by a previous action, text, number or expression to compare with the first operand |

## Output Variables
This action doesn't produce any variables.

## Exceptions
This action doesn't include any exceptions.