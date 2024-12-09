# DateTime Actions

Actions for working with dates and times in Power Automate Desktop. These actions provide the exact, pasteable syntax that works when copied into PAD.

## Important Notes

- Each action must follow the exact syntax pattern:
  ```
  DateTime.Add DateTime: `` TimeToAdd: `` TimeUnit: DateTime.TimeUnit.Seconds ResultedDate=> ResultedDate
  ```
  or
  ```
  DateTime.GetCurrentDateTime DateTime: `` ResultedDate=> CurrentDateTime
  ```

- Always use backticks (``) as placeholders
- Maintain exact spacing and parameter names
- Use Seconds for all time units
- Test any modifications before using

## Available Actions

- [Add to DateTime](./add-to-datetime.md)
- [Get Current DateTime](./get-current-datetime.md)

## Common Time Conversions

- 1 minute = 60 seconds
- 1 hour = 3600 seconds 
- 1 day = 86400 seconds
- 1 week = 604800 seconds
- 1 month (30 days) = 2592000 seconds

When adding time values, convert to seconds for consistent behavior.