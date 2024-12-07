# DateTime Handling Examples

## Working Day Calculation Example

### Description
Calculates the previous working day, accounting for weekends.

### Code
```
# Get current datetime and day of week
DateTime.GetCurrentDateTime.Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> Today
SET Day TO Today.DayOfWeek

# Check if previous day was weekend and adjust accordingly
IF (Day) = ($'''Sunday''') THEN
    DateTime.Add DateTime: Today TimeToAdd: -2 TimeUnit: DateTime.TimeUnit.Days ResultedDate=> BusinessDayBeforeToday
    Text.ConvertDateTimeToText.FromCustomDateTime DateTime: BusinessDayBeforeToday CustomFormat: $'''MMMM''' Result=> BusinessDayBeforeToday_Month
    Display.ShowMessageDialog.ShowMessage Title: $'''%''%''' Message: $'''The last working day was:
Day: %BusinessDayBeforeToday.Day% 
Month: %BusinessDayBeforeToday_Month%
Year: %BusinessDayBeforeToday.Year%''' Icon: Display.Icon.Information Buttons: Display.Buttons.OK DefaultButton: Display.DefaultButton.Button1 IsTopMost: True ButtonPressed=> ButtonPressed
ELSE IF (Day) = ($'''Monday''') THEN
    DateTime.Add DateTime: Today TimeToAdd: -3 TimeUnit: DateTime.TimeUnit.Days ResultedDate=> BusinessDayBeforeToday
    [Rest of the code...]
END
```

### Key Concepts
1. DateTime retrieval
2. Day of week checking
3. Date arithmetic
4. Date formatting

### Best Practices
1. Use clear variable names (Today, BusinessDayBeforeToday)
2. Add explanatory comments for logic
3. Group related operations