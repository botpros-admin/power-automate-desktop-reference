# Add to DateTime

## 🚨 BACKTICKS ARE MANDATORY - MUST USE EXACTLY AS SHOWN 🚨

This is the ONLY valid format - BACKTICKS REQUIRED:

```
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

## ⛔️ THESE ARE ALL WRONG - DO NOT USE:

```
// ❌ WRONG - NO BACKTICKS, USING %VARIABLES%
DateTime.Add DateTime: %CurrentTime% TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> FutureDate

// ❌ WRONG - HAS REGIONS
**REGION AddBusinessDays
DateTime.Add DateTime: %CurrentTime% TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> FutureDate
**ENDREGION

// ❌ WRONG - LINE BREAKS AND NO BACKTICKS
DateTime.Add
  DateTime: %CurrentDateTime%
  TimeToAdd: 432000
  TimeUnit: DateTime.TimeUnit.Seconds
  ResultedDate=> ResultedDate
```

## ✅ THESE ARE THE ONLY CORRECT FORMATS:

```
// ✅ CORRECT - HAS BACKTICKS, ONE LINE
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate

// ✅ CORRECT - HAS BACKTICKS, WITH VALUE
DateTime.Add DateTime: `` TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

## 🔴 ABSOLUTELY REQUIRED:

1. BACKTICKS (``) MUST BE USED FOR DateTime PARAMETER
2. NO %VARIABLES% - USE BACKTICKS INSTEAD
3. NO REGIONS
4. ONE LINE ONLY
5. EXACT SPACING
6. EXACT PARAMETER NAMES
7. EXACT VARIABLE NAMES
8. TimeUnit MUST BE DateTime.TimeUnit.Seconds

## Time Conversions

When specifying TimeToAdd, convert to seconds:
- 1 minute = 60 seconds
- 1 hour = 3600 seconds
- 1 day = 86400 seconds
- 5 days = 432000 seconds
- 1 week = 604800 seconds
- 30 days = 2592000 seconds