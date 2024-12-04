# Send Mouse Click

## Description
Sends a mouse click event with various click types and options.

## Syntax
```
MouseAndKeyboard.SendMouseClick.Click ClickType: MouseAndKeyboard.MouseClickType.LeftClick MillisecondsDelay: 0
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Mouse event to send | Yes | Enum | Left click | Options: Left click, Right click, Double click, Middle click, Left button down, Left button up, Right button down, Right button up |
| Wait | No | Numeric value | 0 | The time to delay before sending the mouse event in 1/1000 of a second |
| Move mouse | No | Boolean | False | Whether to move mouse |
| X | Yes (if Move mouse) | Numeric value | - | The horizontal (X) position of the mouse in pixel coordinates |
| Y | Yes (if Move mouse) | Numeric value | - | The vertical (Y) position of the mouse in pixel coordinates |
| Relative to | Yes (if Move mouse) | Enum | Screen | Options: Screen, Active window, Current mouse position |
| Mouse movement style | Yes (if Move mouse) | Enum | Instant | Options: Instant, With animation (low/normal/high speed) |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Can't send mouse click in non interactive mode | Indicates a problem sending a mouse click in non-interactive mode |
| Mouse click out of screen bounds | Indicates that the mouse click was out of the screen bounds |
| Failed to send mouse click | Indicates a problem sending a mouse click |

## Example Usage

```powershell
# Simple left click
MouseAndKeyboard.SendMouseClick.Click ClickType: MouseAndKeyboard.MouseClickType.LeftClick MillisecondsDelay: 0

# Right click with movement
MouseAndKeyboard.SendMouseClick.ClickWithMove ClickType: MouseAndKeyboard.MouseClickType.RightClick X: 100 Y: 200 RelativeTo: MouseAndKeyboard.PositionRelativeTo.Screen MovementStyle: MouseAndKeyboard.MovementStyle.Normal
```

## Best Practices
1. Use appropriate delays for target application responsiveness
2. Consider screen resolution when using absolute coordinates
3. Handle non-interactive mode scenarios
4. Use relative positioning when possible
5. Implement error handling for out-of-bounds scenarios