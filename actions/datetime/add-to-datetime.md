# Add to DateTime

## Description
Adds or subtracts a specified interval to/from a datetime value.

## Syntax
```
DateTime.Add DateTime: `[date]` TimeToAdd: `[value]` TimeUnit: DateTime.TimeUnit.Days ResultedDate=> ResultDate
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| DateTime | Yes | DateTime | - | Base date to modify |
| TimeToAdd | Yes | Numeric value | - | Amount to add/subtract |
| TimeUnit | Yes | Years, Months, Days, Hours, Minutes, Seconds | Days | Unit of time to add |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| ResultDate | DateTime | The resulting date and time |

## Exceptions
This action doesn't include any exceptions.