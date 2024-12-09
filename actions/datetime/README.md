# DateTime Actions

## 🚨 MANDATORY BACKTICKS AND EXACT FORMAT - READ FIRST 🚨

### ‼️ THE BACKTICKS (``) ARE REQUIRED - DO NOT REMOVE THEM ‼️

1. Getting current time - BACKTICKS REQUIRED:
```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

2. Adding time - BACKTICKS REQUIRED:
```
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

### ⛔️ THESE ARE WRONG - THEY WILL NOT WORK:

```
// ❌ WRONG - NO BACKTICKS
DateTime.GetCurrentDateTime DateTime: Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> CurrentTime

// ❌ WRONG - NO BACKTICKS AND HAS REGIONS
**REGION InitializeCurrentTime
DateTime.GetCurrentDateTime Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> CurrentTime
**ENDREGION

// ❌ WRONG - USING %Variables% INSTEAD OF BACKTICKS
DateTime.Add DateTime: %CurrentTime% TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> FutureDate
```

### ✅ THESE ARE THE ONLY CORRECT FORMATS:

```
// ✅ CORRECT - HAS BACKTICKS
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime

// ✅ CORRECT - HAS BACKTICKS
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

### 🔴 ABSOLUTELY REQUIRED:

1. BACKTICKS (``) MUST BE USED AS SHOWN
2. NO %VARIABLES% - USE BACKTICKS INSTEAD
3. NO REGIONS
4. NO DateTimeFormat parameter
5. NO Local parameter
6. NO line breaks
7. NO extra parameters
8. NO different variable names

## Time Conversions

When using DateTime.Add, convert all times to seconds:
- 1 minute = 60 seconds
- 1 hour = 3600 seconds
- 1 day = 86400 seconds
- 5 days = 432000 seconds
- 1 week = 604800 seconds
- 30 days = 2592000 seconds