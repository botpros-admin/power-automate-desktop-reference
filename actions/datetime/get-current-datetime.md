# Get Current DateTime

## Description
Gets the current system date and time.

## Syntax
```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

## Input Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| DateTime | Yes | Placeholder - use backticks |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CurrentDateTime | DateTime | The current system date and time |

## Example Usage

### Get Current Date and Time
```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

### Get Current Date/Time Then Add One Day
```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
DateTime.Add DateTime: `` TimeToAdd: 86400 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> TomorrowDateTime
```

## Notes

- The current time is based on the system clock
- Use this action when you need a reference point for date/time calculations
- Combine with DateTime.Add for relative time calculations
- Always maintain exact syntax with backticks as shown