# Get Window Action

## Description
Gets a running window, for automating desktop applications.

## Syntax
```
UIAutomation.GetWindow.GetUseTimeout Control: `` BringWindowToFront: False Timeout: 5 WindowInstance=> AutomationWindow
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Get window | Yes | Enum | Specific window | Options: Specific window, Foreground window |
| UI element | Yes (if specific window) | UI element | - | The selector of the window to get |
| Bring window to front | No | Boolean | False | Whether to bring the window to the foreground automatically upon acquiring it |
| Fail if window isn't found | No | Boolean | True | Whether to wait indefinitely for the window to appear or fail after timeout |
| Timeout | Yes (if fail if not found) | Numeric | - | The timeout to wait in seconds |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| WindowTitle | Text value | The title of the foreground window |
| AutomationWindow | Window instance | The specific window instance for use with later UI Automation actions |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to get window | Indicates a problem getting the window |

## Example Usage

```powershell
# Get specific window with timeout
UIAutomation.GetWindow.GetUseTimeout Control: %NotePadWindow% BringWindowToFront: True Timeout: 10 WindowInstance=> NotepadInstance

# Get foreground window
UIAutomation.GetWindow.GetForegroundWindow WindowInstance=> ActiveWindow
```

## Best Practices
1. Use appropriate timeouts for different scenarios
2. Handle window not found scenarios
3. Consider whether bringing window to front is necessary
4. Store window instance for reuse
5. Verify window state before performing actions