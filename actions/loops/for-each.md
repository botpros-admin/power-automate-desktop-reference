# For Each

## Description
Iterates over items in a list, data table or data row, allowing a block of actions to be executed repeatedly.

## Syntax
```
LOOP FOREACH CurrentItem IN `[collection]`
END
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Value to iterate | Yes | * | - | Enter a list, data row, or data table value to iterate through it |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| * | [Same as item type] | The value name that will store the current item value in each iteration |

## Exceptions
This action doesn't include any exceptions.