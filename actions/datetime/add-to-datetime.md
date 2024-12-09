# Add to DateTime

## CRITICAL: EXACT SYNTAX

This action MUST be written on a single line exactly as shown:

```
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

## Description
Adds a specified amount of time to a date/time value.

## Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| DateTime | Yes | Must use backticks exactly as shown |
| TimeToAdd | Yes | Must use backticks or numeric value |
| TimeUnit | Yes | Must be exactly DateTime.TimeUnit.Seconds |
| ResultedDate=> | Yes | Must be written exactly as shown |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| ResultedDate | DateTime | The resulting date/time |

## Examples - CORRECT FORMAT

✅ CORRECT - Single line with 5 days (432000 seconds):
```
DateTime.Add DateTime: `` TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

✅ CORRECT - Single line with 1 hour (3600 seconds):
```
DateTime.Add DateTime: `` TimeToAdd: 3600 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

## Examples - WRONG FORMATS

❌ WRONG - Do not use regions or indentation:
```
**REGION AddTime
DateTime.Add
  DateTime: %CurrentDateTime%
  TimeToAdd: 432000
  TimeUnit: DateTime.TimeUnit.Seconds
  ResultedDate => FutureDateTime
**ENDREGION
```

❌ WRONG - Do not break into multiple lines:
```
DateTime.Add
  DateTime: `` 
  TimeToAdd: 432000
  TimeUnit: DateTime.TimeUnit.Seconds
  ResultedDate => ResultedDate
```

❌ WRONG - Do not add comments or extra formatting:
```
// Add 5 days
DateTime.Add DateTime: %CurrentDateTime% TimeToAdd: 432000  // in seconds
```

## Common Time Conversions

- 1 minute = 60 seconds
- 1 hour = 3600 seconds
- 1 day = 86400 seconds
- 5 days = 432000 seconds
- 1 week = 604800 seconds
- 30 days = 2592000 seconds

## Notes

- Must be a single line
- Must use exact spacing
- Must use backticks (``) as shown
- Must use Seconds as TimeUnit
- No comments or extra formatting
- No regions or indentation