# Add to DateTime

## Description
Adds a specified amount of time to a date/time value.

## Syntax
```
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

## Input Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| DateTime | Yes | The date/time value to add to (use backticks) |
| TimeToAdd | Yes | Amount of time to add in seconds (numeric value) |
| TimeUnit | Yes | Must be DateTime.TimeUnit.Seconds |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| ResultedDate | DateTime | The resulting date/time value |

## Examples

### Add 5 Days
```
DateTime.Add DateTime: `` TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

### Add 30 Minutes
```
DateTime.Add DateTime: `` TimeToAdd: 1800 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

### Add 1 Hour
```
DateTime.Add DateTime: `` TimeToAdd: 3600 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

## Important Notes

- Always use Seconds as the TimeUnit for consistent behavior
- Maintain exact syntax pattern with backticks as shown
- Convert your desired time to seconds before using:
  - Minutes × 60
  - Hours × 3600
  - Days × 86400
  - Weeks × 604800
  - Months (30 days) × 2592000