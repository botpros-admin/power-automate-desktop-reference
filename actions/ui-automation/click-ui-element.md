# Click UI Element in Window

## Description
Clicks on any UI element of a window with various click types and positioning options.

## Syntax
```
UIAutomation.Click.Click Element: `` ClickType: UIAutomation.ClickType.LeftClick MousePositionRelativeToElement: UIAutomation.RectangleEdgePoint.MiddleCenter OffsetX: 0 OffsetY: 0
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| UI element | Yes | UI element | - | The UI element to click on |
| Click type | Yes | Enum | LeftClick | Options: LeftClick, RightClick, DoubleClick, MiddleClick, LeftButtonDown, LeftButtonUp, RightButtonDown, RightButtonUp |
| Simulate action | No | Boolean | False | Whether to simulate the move of the mouse cursor over the element prior to clicking |
| Mouse position relative to UI element | Yes | Enum | MiddleCenter | Options: TopLeft, TopCenter, TopRight, MiddleLeft, MiddleCenter, MiddleRight, BottomLeft, BottomCenter, BottomRight |
| Offset X | No | Text value | 0 | Offset the mouse from the position by this many pixels to the right |
| Offset Y | No | Text value | 0 | Offset the mouse from the position by this many pixels down |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Click failed | Indicates that the click failed |

## Example Usage

```powershell
# Simple left click
UIAutomation.Click.Click Element: %ButtonElement% ClickType: UIAutomation.ClickType.LeftClick MousePositionRelativeToElement: UIAutomation.RectangleEdgePoint.MiddleCenter OffsetX: 0 OffsetY: 0

# Right click with offset
UIAutomation.Click.Click Element: %MenuElement% ClickType: UIAutomation.ClickType.RightClick MousePositionRelativeToElement: UIAutomation.RectangleEdgePoint.TopRight OffsetX: 5 OffsetY: 5
```

## Best Practices
1. Always verify UI element exists before clicking
2. Use appropriate click type for the action needed
3. Consider using simulation for problematic elements
4. Handle exceptions appropriately
5. Use offsets when precise positioning is required