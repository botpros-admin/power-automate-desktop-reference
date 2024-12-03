# Populate Text Field Action

## Description
Fills a text box in a window with the specified text.

## Syntax
```
UIAutomation.PopulateTextField.PopulateTextField TextField: `` Text: `` Mode: UIAutomation.PopulateTextMode.Replace ClickType: UIAutomation.PopulateMouseClickType.SingleClick
```

## Parameters
- TextField (Required): The text box to populate
- Text (Required): The text to fill in the text field
- Mode: Replace text or Append text (Default: Replace)
- ClickType: Left-click, Double-click, No click (Default: Left-click)

## Example
```powershell
# Fill in a username field
UIAutomation.PopulateTextField.PopulateTextField TextField: "[User ID Field]" Text: "JohnDoe" Mode: UIAutomation.PopulateTextMode.Replace ClickType: UIAutomation.PopulateMouseClickType.SingleClick

# Append text to existing content
UIAutomation.PopulateTextField.PopulateTextField TextField: "[Notes Field]" Text: "Additional note" Mode: UIAutomation.PopulateTextMode.Append ClickType: UIAutomation.PopulateMouseClickType.SingleClick
```

## Exceptions
- Failed to write in textbox