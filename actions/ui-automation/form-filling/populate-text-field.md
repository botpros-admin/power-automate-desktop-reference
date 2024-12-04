# Populate Text Field in Window

## Description
Fills a text box in a window with the specified text.

## Syntax
```
UIAutomation.PopulateTextField.PopulateTextField TextField: `` Text: `` Mode: UIAutomation.PopulateTextMode.Replace ClickType: UIAutomation.PopulateMouseClickType.SingleClick
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Text box | Yes | UI element | - | The text box to populate |
| Text to fill in | Yes | Text value | - | The text to fill in |
| Simulate action | No | Boolean | False | Whether to simulate keystrokes |
| If field isn't empty | No | Enum | Replace text | Replace text or Append text |
| Click before populating | No | Enum | Left-click | Left-click, Double-click, or No |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to write in textbox | Problem populating the text field |

## Example Usage

```powershell
# Simple text input
UIAutomation.PopulateTextField.PopulateTextField TextField: %UsernameField% Text: "JohnDoe" Mode: UIAutomation.PopulateTextMode.Replace

# Append text with simulation
UIAutomation.PopulateTextField.PopulateTextField TextField: %NotesField% Text: "Additional info" Mode: UIAutomation.PopulateTextMode.Append Simulate: True
```

## Best Practices
1. Verify field is editable before input
2. Handle special characters appropriately
3. Consider using simulation for problematic applications
4. Verify input success
5. Clear field when replacing text
6. Use appropriate waits after input