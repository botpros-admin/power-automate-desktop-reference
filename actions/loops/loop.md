# Loop

## Description
Iterates a block of actions for a specified number of times

## Syntax
```
LOOP LoopIndex FROM `[start]` TO `[end]` STEP `[increment]`
END
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Start from | Yes | Numeric value | - | Set the starting point of the loop counter |
| Increment by | Yes | Numeric value | - | Set the increment that the loop counter variable is increased by |
| End to | Yes | Numeric value | - | Set the ending point of the loop counter |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| * | Numeric value | The value name that will store the current index, starting at the start from value. The value will change by the increment with each iteration |

## Exceptions
This action doesn't include any exceptions.