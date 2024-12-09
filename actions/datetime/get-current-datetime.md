# Get Current DateTime

## 🚨 EXACT SYNTAX REQUIRED - NO VARIATIONS ALLOWED 🚨

This is the ONLY valid syntax:

```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

### ❌ THESE ARE ALL WRONG:

```
❌ WRONG - DO NOT ADD .Local:
DateTime.GetCurrentDateTime.Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> %CurrentDate%

❌ WRONG - DO NOT USE REGIONS:
**REGION Initialize
DateTime.GetCurrentDateTime.Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> %CurrentDate%
**ENDREGION

❌ WRONG - DO NOT USE DateTimeFormat:
DateTime.GetCurrentDateTime DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> CurrentDateTime

❌ WRONG - DO NOT USE %VARIABLES%:
DateTime.GetCurrentDateTime DateTime: %CurrentDate% ResultedDate=> CurrentDateTime

❌ WRONG - DO NOT USE $''' SYNTAX:
DateTime.GetCurrentDateTime DateTime: $'''%CurrentDate%''' ResultedDate=> CurrentDateTime
```

### ✅ THIS IS THE ONLY CORRECT SYNTAX:

```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

### 🔴 ABSOLUTE REQUIREMENTS:

1. MUST use DateTime: ``
2. MUST use ResultedDate=>
3. MUST use CurrentDateTime as variable name
4. NO .Local suffix
5. NO DateTimeFormat parameter
6. NO %variables%
7. NO $''' syntax
8. NO regions
9. ONE line only
10. EXACT spacing