# Add to DateTime

## 🚨 EXACT SYNTAX REQUIRED - NO VARIATIONS ALLOWED 🚨

This is the ONLY valid syntax:

```
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

### ❌ THESE ARE ALL WRONG:

```
❌ WRONG - DO NOT USE REGIONS:
**REGION AddBusinessDays
DateTime.Add DateTime: %CurrentDate% TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> %FutureDate%
**ENDREGION

❌ WRONG - DO NOT USE %VARIABLES%:
DateTime.Add DateTime: %CurrentDate% TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> %FutureDate%

❌ WRONG - DO NOT USE $''' SYNTAX:
DateTime.Add DateTime: $'''%CurrentDate%''' TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate

❌ WRONG - DO NOT USE LINE BREAKS:
DateTime.Add 
  DateTime: %CurrentDateTime%
  TimeToAdd: 432000
  TimeUnit: DateTime.TimeUnit.Seconds
  ResultedDate=> ResultedDate
```

### ✅ THESE ARE THE ONLY CORRECT FORMATS:

```
✅ CORRECT - Using placeholders:
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate

✅ CORRECT - With 5 days (432000 seconds):
DateTime.Add DateTime: `` TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

### 🔴 ABSOLUTE REQUIREMENTS:

1. MUST use DateTime: ``
2. MUST use TimeToAdd: (with either `` or a number)
3. MUST use TimeUnit: DateTime.TimeUnit.Seconds
4. MUST use ResultedDate=> ResultedDate
5. NO %variables%
6. NO $''' syntax
7. NO regions
8. ONE line only
9. EXACT spacing
10. EXACT parameter names