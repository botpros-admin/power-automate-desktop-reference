# Power Automate Desktop Best Practices

## Flow Structure

### 1. Error Handling
- Use block error handling
- Log errors appropriately
- Clean up resources on error
- Use appropriate timeouts
- Handle expected exceptions

### 2. Variables
- Use descriptive names
- Initialize variables properly
- Clean up large variables
- Use appropriate data types
- Document variable purposes

### 3. Flow Organization
- Use regions for logical grouping
- Create reusable subflows
- Comment complex logic
- Use consistent naming
- Maintain modularity

### 4. Performance
- Minimize external calls
- Use appropriate waits
- Clean up resources
- Optimize loops
- Handle large datasets efficiently

### 5. UI Automation
- Use reliable selectors
- Handle timeouts appropriately
- Include error recovery
- Verify UI states
- Handle window focus

## Common Patterns

### Error Handling Block
```powershell
BLOCK "Operation Name"
ON BLOCK ERROR
    # Log error
    # Cleanup
    # Notify if needed
END
    # Main operations
END
```

### Resource Cleanup
```powershell
# Always close connections
TRY
    # Operation
FINALLY
    # Cleanup
END
```

### UI Automation
```powershell
# Wait for element with timeout
UI.WaitForElement Element: %Button% Timeout: 30
IF UI.ElementExists(Element: %Button%) THEN
    UI.ClickElement Element: %Button%
END
```