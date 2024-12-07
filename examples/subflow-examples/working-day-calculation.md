# Working Day Calculation Example

## Description
Calculates the previous working day, accounting for weekends.

## Code
```
# Get current datetime and day of week
DateTime.GetCurrentDateTime.Local DateTimeFormat: DateTime.DateTimeFormat.DateAndTime CurrentDateTime=> Today
SET Day TO Today.DayOfWeek

# Check for weekend and adjust accordingly
IF (Day) = ($'''Sunday''') THEN
    # If Sunday, go back 2 days to Friday
    DateTime.Add DateTime: Today TimeToAdd: -2 TimeUnit: DateTime.TimeUnit.Days ResultedDate=> BusinessDayBeforeToday
    Text.ConvertDateTimeToText.FromCustomDateTime DateTime: BusinessDayBeforeToday CustomFormat: $'''MMMM''' Result=> BusinessDayBeforeToday_Month
    Display.ShowMessageDialog.ShowMessage Title: $'''%''%''' Message: $'''The last working day was:
Day: %BusinessDayBeforeToday.Day% 
Month: %BusinessDayBeforeToday_Month%
Year: %BusinessDayBeforeToday.Year%''' Icon: Display.Icon.Information Buttons: Display.Buttons.OK DefaultButton: Display.DefaultButton.Button1 IsTopMost: True ButtonPressed=> ButtonPressed
ELSE IF (Day) = ($'''Monday''') THEN
    # If Monday, go back 3 days to Friday
    DateTime.Add DateTime: Today TimeToAdd: -3 TimeUnit: DateTime.TimeUnit.Days ResultedDate=> BusinessDayBeforeToday
    Text.ConvertDateTimeToText.FromCustomDateTime DateTime: BusinessDayBeforeToday CustomFormat: $'''MMMM''' Result=> BusinessDayBeforeToday_Month
    Display.ShowMessageDialog.ShowMessage Title: $'''%''%''' Message: $'''The last working day was:
Day: %BusinessDayBeforeToday.Day% 
Month: %BusinessDayBeforeToday_Month%
Year: %BusinessDayBeforeToday.Year%''' Icon: Display.Icon.Information Buttons: Display.Buttons.OK DefaultButton: Display.DefaultButton.Button1 IsTopMost: True ButtonPressed=> ButtonPressed
ELSE
    # For other days, just go back 1 day
    DateTime.Add DateTime: Today TimeToAdd: -1 TimeUnit: DateTime.TimeUnit.Days ResultedDate=> BusinessDayBeforeToday
    Text.ConvertDateTimeToText.FromCustomDateTime DateTime: BusinessDayBeforeToday CustomFormat: $'''MMMM''' Result=> BusinessDayBeforeToday_Month
    Display.ShowMessageDialog.ShowMessage Title: $'''%''%''' Message: $'''The last working day was:
Day: %BusinessDayBeforeToday.Day% 
Month: %BusinessDayBeforeToday_Month%
Year: %BusinessDayBeforeToday.Year%''' Icon: Display.Icon.Information Buttons: Display.Buttons.OK DefaultButton: Display.DefaultButton.Button1 IsTopMost: True ButtonPressed=> ButtonPressed
END
```

## Key Features
1. Inline comments explaining logic
2. Clear variable naming
3. Consistent message formatting
4. Proper date handling