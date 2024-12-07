# Get Current DateTime

## Description
Retrieves the current date and time in local or UTC format.

## Syntax
```
DateTime.GetCurrentDateTime.Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> CurrentDateTime
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| DateTimeFormat | Yes | DateAndTime, DateOnly, TimeOnly | DateAndTime | Format of datetime output |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CurrentDateTime | DateTime | The current date and time |

## Exceptions
This action doesn't include any exceptions.