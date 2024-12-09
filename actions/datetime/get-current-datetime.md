# Get Current DateTime

## ‼️ MANDATORY EXACT FORMAT - NO EXCEPTIONS ‼️

This action has ONE valid format. It MUST be written EXACTLY as shown below:

```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
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
- NO DateTimeFormat parameter

## ⛔ FORBIDDEN FORMATS - These Will NOT Work:

```
// WRONG - Regions not allowed
**REGION GetCurrentDateTime**
DateTime.GetCurrentDateTime DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> CurrentDate
**ENDREGION**

// WRONG - Extra parameters not allowed
DateTime.GetCurrentDateTime DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> CurrentDate

// WRONG - Different parameter names
DateTime.GetCurrentDateTime Date: `` Result=> CurrentDate

// WRONG - Line breaks not allowed
DateTime.GetCurrentDateTime
  DateTime: ``
  ResultedDate=> CurrentDateTime
```

## ✅ The ONLY Valid Format:

```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CurrentDateTime | DateTime | The current system date and time |

## Critical Notes

- You MUST use this EXACT format
- You MUST use CurrentDateTime as the output variable name
- You MUST keep it on one line
- You MUST NOT add any extra parameters or formatting
- You MUST NOT use regions or comments