# Get Current DateTime

## CRITICAL: EXACT SYNTAX

This action MUST be written on a single line exactly as shown:

```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

## Description
Gets the current system date and time.

## Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| DateTime | Yes | Must be written with backticks exactly as shown |
| ResultedDate=> | Yes | Must be written exactly as shown |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CurrentDateTime | DateTime | The current system date and time |

## Example - CORRECT FORMAT

✅ CORRECT - Single line with exact spacing:
```
DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
```

## Examples - WRONG FORMATS

❌ WRONG - Do not use regions or indentation:
```
**REGION Initialize
DateTime.GetCurrentDateTime
  DateTime => CurrentDateTime
**ENDREGION
```

❌ WRONG - Do not break into multiple lines:
```
DateTime.GetCurrentDateTime
  DateTime: `` 
  ResultedDate => CurrentDateTime
```

❌ WRONG - Do not add comments or extra formatting:
```
// Get current date
DateTime.GetCurrentDateTime DateTime => CurrentDateTime
```

## Notes

- Must be a single line
- Must use exact spacing
- Must use backticks (``) as shown
- No comments or extra formatting
- No regions or indentation