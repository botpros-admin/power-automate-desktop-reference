# Get Current DateTime

## 🚨 BACKTICKS ARE MANDATORY - MUST USE EXACTLY AS SHOWN 🚨

This is the ONLY valid format - BACKTICKS REQUIRED:

```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

## ⛔️ THESE ARE ALL WRONG - DO NOT USE:

```
// ❌ WRONG - NO BACKTICKS
DateTime.GetCurrentDateTime Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> CurrentTime

// ❌ WRONG - HAS REGIONS AND NO BACKTICKS
**REGION InitializeCurrentTime
DateTime.GetCurrentDateTime Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> CurrentTime
**ENDREGION

// ❌ WRONG - USING %VARIABLES% INSTEAD OF BACKTICKS
DateTime.GetCurrentDateTime DateTime: %CurrentTime% ResultedDate=> CurrentDateTime
```

## ✅ THIS IS THE ONLY CORRECT FORMAT:

```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

## 🔴 ABSOLUTELY REQUIRED:

1. BACKTICKS (``) MUST BE USED EXACTLY AS SHOWN
2. NO %VARIABLES% - USE BACKTICKS INSTEAD
3. NO REGIONS
4. NO DateTimeFormat parameter
5. NO Local parameter
6. ONE LINE ONLY
7. EXACT SPACING
8. EXACT PARAMETER NAMES
9. EXACT VARIABLE NAMES

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CurrentDateTime | DateTime | The current system date and time |