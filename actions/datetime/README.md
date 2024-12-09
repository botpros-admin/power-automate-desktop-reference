# DateTime Actions

## CRITICAL: EXACT SYNTAX FORMAT

Every action MUST be on a single line with EXACT spacing and NO line breaks. The following are the ONLY valid formats:

For getting current date/time:
```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

For adding time:
```
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

## Forbidden Formats

DO NOT output in any of these formats as they are not pasteable:

❌ WRONG - Do not use indentation or multi-line format:
```
DateTime.Add
  DateTime: %CurrentDateTime%
  TimeToAdd: 432000
  TimeUnit: DateTime.TimeUnit.Seconds
  ResultedDate => FutureDateTime
```

❌ WRONG - Do not use regions:
```
**REGION Initialize
DateTime.GetCurrentDateTime
  DateTime => CurrentDateTime
**ENDREGION
```

❌ WRONG - Do not add comments or extra formatting:
```
DateTime.Add
  DateTime: %CurrentDateTime%
  TimeToAdd: 432000  // 5 business days in seconds
  TimeUnit: DateTime.TimeUnit.Seconds
```

## Common Time Conversions

- 1 minute = 60 seconds
- 1 hour = 3600 seconds 
- 1 day = 86400 seconds
- 5 days = 432000 seconds
- 1 week = 604800 seconds
- 1 month (30 days) = 2592000 seconds

## Available Actions

- [Add to DateTime](./add-to-datetime.md)
- [Get Current DateTime](./get-current-datetime.md)