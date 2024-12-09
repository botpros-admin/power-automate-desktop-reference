# DateTime Actions

## ‼️ CRITICAL FORMATTING RULES - READ THIS FIRST ‼️

### The ONLY Two Valid Formats:

1. For getting current date/time, this EXACT line and NOTHING else:
```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

2. For adding time, this EXACT line and NOTHING else:
```
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

### ⛔ ABSOLUTELY FORBIDDEN - DO NOT USE:

- NO REGIONS (never use **REGION** or **ENDREGION**)
- NO DateTimeFormat parameter (do not include DateTimeFormat: DateTime.DateTimeFormat.DateAndTime)
- NO comments
- NO line breaks
- NO extra spaces
- NO additional parameters
- NO different parameter names
- NO different variable names than shown above
- NO alternative syntaxes

### 🚫 Examples of INCORRECT Formats That Will NOT Work:

```
// WRONG - Regions not allowed
**REGION GetCurrentDateTime**
DateTime.GetCurrentDateTime DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> CurrentDate
**ENDREGION**

// WRONG - Extra parameters not allowed
DateTime.GetCurrentDateTime DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> CurrentDate

// WRONG - Different variable names
DateTime.Add DateTime: %CurrentDate% TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> FutureDate

// WRONG - Line breaks not allowed
DateTime.Add 
  DateTime: %CurrentDateTime% 
  TimeToAdd: 432000
  TimeUnit: DateTime.TimeUnit.Seconds
  ResultedDate=> ResultedDate
```

### ✅ The ONLY Valid Examples:

```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

```
DateTime.Add DateTime: `` TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

## Time Conversions Reference

When using DateTime.Add, convert all times to seconds:

- 1 minute = 60 seconds
- 1 hour = 3600 seconds
- 1 day = 86400 seconds
- 5 days = 432000 seconds
- 1 week = 604800 seconds
- 30 days = 2592000 seconds

## Available Actions

- [Add to DateTime](./add-to-datetime.md)
- [Get Current DateTime](./get-current-datetime.md)