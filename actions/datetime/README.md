# DateTime Actions

## 🚨 MANDATORY EXACT SYNTAX - READ THIS FIRST 🚨

### ⚠️ These Are The ONLY TWO Valid Syntax Patterns:

1. Getting current time:
```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

2. Adding time:
```
DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

### ❌ THESE PATTERNS ARE WRONG AND WILL NOT WORK:

```
❌ WRONG - DO NOT USE REGIONS:
**REGION Initialize
DateTime.GetCurrentDateTime.Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> %CurrentDate%
**ENDREGION

❌ WRONG - DO NOT USE .Local OR DateTimeFormat:
DateTime.GetCurrentDateTime.Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> %CurrentDate%

❌ WRONG - DO NOT USE %VARIABLES%:
DateTime.Add DateTime: %CurrentDate% TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> %FutureDate%

❌ WRONG - DO NOT USE $''' SYNTAX:
DateTime.GetCurrentDateTime DateTime: $'''%CurrentDate%''' ResultedDate=> CurrentDateTime
```

### ✅ COPY THESE PATTERNS EXACTLY:

To get current date/time, use EXACTLY:
```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

To add time (like 5 days = 432000 seconds), use EXACTLY:
```
DateTime.Add DateTime: `` TimeToAdd: 432000 TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
```

### 🔴 SYNTAX REQUIREMENTS:

1. NO regions (**REGION**, **ENDREGION**)
2. NO .Local suffix
3. NO DateTimeFormat parameter
4. NO %variables% - use backticks (``) instead
5. NO $''' syntax
6. NO line breaks
7. MUST use ResultedDate=> (not CurrentDateTime=>)
8. MUST use DateTime: (not Date:)
9. MUST follow spacing exactly
10. MUST use parameter names exactly as shown