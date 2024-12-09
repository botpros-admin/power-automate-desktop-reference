# Add to DateTime

## ‼️ MANDATORY EXACT FORMAT - NO EXCEPTIONS ‼️

This action has ONE valid format. It MUST be written EXACTLY as shown below:

```
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

This means:
- ONE line only
- EXACT spacing (one space after each colon)
- EXACT parameter names
- EXACT variable names
- NO additional parameters
- NO regions
- NO comments
- NO line breaks
- TimeUnit MUST be DateTime.TimeUnit.Seconds

## ⛔ FORBIDDEN FORMATS - These Will NOT Work:

```
// WRONG - Regions not allowed
**REGION AddBusinessDays**
DateTime.Add DateTime: %CurrentDate% TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> FutureDate
**ENDREGION**

// WRONG - Different variable names
DateTime.Add DateTime: %CurrentDate% TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> FutureDate

// WRONG - Line breaks not allowed
DateTime.Add
  DateTime: ``
  TimeToAdd: 432000
  TimeUnit: DateTime.TimeUnit.Seconds
  ResultedDate=> ResultedDate
```

## ✅ The ONLY Valid Examples:

```
DateTime.Add DateTime: `` TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

## Time Conversions

When specifying TimeToAdd, convert your time to seconds:

- 1 minute = 60 seconds
- 1 hour = 3600 seconds
- 1 day = 86400 seconds
- 5 days = 432000 seconds
- 1 week = 604800 seconds
- 30 days = 2592000 seconds

## Critical Notes

- You MUST use this EXACT format
- You MUST use ResultedDate as the output variable name
- You MUST keep it on one line
- You MUST use DateTime.TimeUnit.Seconds
- You MUST NOT add any extra parameters or formatting
- You MUST NOT use regions or comments