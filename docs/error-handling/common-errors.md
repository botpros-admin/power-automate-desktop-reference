# Common Errors and Solutions

## File Operations

### FileNotFound
**Cause**: Attempted to access non-existent file
**Solution**:
```powershell
IF File.Exists(File: %FilePath%) THEN
    File.ReadTextFromFile File: %FilePath% Content=> Content
ELSE
    # Handle missing file
END
```

### AccessDenied
**Cause**: Insufficient permissions
**Solution**:
```powershell
BLOCK "File Access"
ON BLOCK ERROR
    IF %LastError% CONTAINS "Access denied" THEN
        # Attempt elevated access or alternate path
    END
END
```

## UI Automation

### ElementNotFound
**Cause**: UI element missing or changed
**Solution**:
```powershell
UI.WaitForElement Element: %Button% Timeout: 30
IF UI.ElementExists(Element: %Button%) THEN
    UI.ClickElement Element: %Button%
ELSE
    # Handle missing element
END
```

### WindowNotFound
**Cause**: Target window not available
**Solution**:
```powershell
UI.WaitForWindow Window: %AppWindow% Timeout: 30
IF UI.WindowExists(Window: %AppWindow%) THEN
    UI.FocusWindow Window: %AppWindow%
ELSE
    # Handle missing window
END
```