# Error Handling in Power Automate Desktop

## Overview
Comprehensive guide to implementing robust error handling in PAD flows.

## Error Handling Mechanisms

### 1. Block Error Handling
```powershell
BLOCK "Operation Name"
ON BLOCK ERROR
    # Error handling logic
    Variables.SetVariable ErrorDetails: %LastError%
    System.LogMessage "Error in operation: %ErrorDetails%"
    # Cleanup operations
END
    # Main operations
END
```

### 2. Try-Catch Pattern
```powershell
TRY
    # Risky operation
    File.ReadTextFromFile File: %InputFile% Content=> FileContent
CATCH FileNotFound
    # Handle specific error
    System.LogMessage "File not found: %InputFile%"
CATCH
    # Handle any other error
    System.LogMessage "Unexpected error: %LastError%"
END
```

### 3. Conditional Error Checking
```powershell
IF File.Exists(File: %FilePath%) THEN
    # Safe to proceed
    File.ReadTextFromFile File: %FilePath% Content=> Content
ELSE
    # Handle missing file
    System.LogMessage "File missing: %FilePath%"
END
```

## Common Error Scenarios

### 1. File Operations
- File not found
- Access denied
- File in use
- Invalid path
- Disk full

### 2. UI Automation
- Element not found
- Window not found
- Click failed
- Timeout
- State mismatch

### 3. Network Operations
- Connection failed
- Timeout
- Authentication failed
- Invalid response
- Service unavailable

## Best Practices

### 1. Error Prevention
- Validate inputs
- Check preconditions
- Use appropriate timeouts
- Handle edge cases
- Implement retries

### 2. Error Recovery
- Clean up resources
- Restore state
- Notify appropriate parties
- Log details
- Implement fallbacks

### 3. Error Logging
```powershell
# Structured error logging
Variables.SetVariable LogEntry: {
    "timestamp": %CurrentDateTime%,
    "operation": "FileRead",
    "error": %LastError%,
    "details": {
        "file": %FilePath%,
        "attempt": %RetryCount%
    }
}
System.LogMessage %LogEntry%
```

## Error Handling Patterns

### 1. Retry Pattern
```powershell
Variables.SetVariable RetryCount: 0
Variables.SetVariable MaxRetries: 3

LABEL "RetryOperation"
BLOCK "Operation with Retry"
ON BLOCK ERROR
    Variables.IncreaseVariable Value: %RetryCount% IncrementValue: 1
    IF RetryCount < MaxRetries THEN
        System.LogMessage "Retry attempt %RetryCount%"
        System.Wait Seconds: 5
        GOTO "RetryOperation"
    ELSE
        THROW ERROR
    END
END
    # Main operation
END
```

### 2. Cleanup Pattern
```powershell
BLOCK "Main Operation"
ON BLOCK ERROR
    # Error handler
    GOTO "Cleanup"
END
    # Main operations
END

LABEL "Cleanup"
# Cleanup operations
```

### 3. Transaction Pattern
```powershell
BLOCK "Transaction"
ON BLOCK ERROR
    # Rollback changes
    GOTO "Rollback"
END
    # Transaction operations
END

LABEL "Rollback"
# Rollback operations
```

## Error Documentation

### 1. Log Format
```json
{
    "timestamp": "2024-12-03T10:00:00",
    "level": "ERROR",
    "operation": "FileRead",
    "error": {
        "type": "FileNotFound",
        "message": "File 'input.txt' not found",
        "details": {
            "path": "C:\\data\\input.txt",
            "attempt": 1
        }
    },
    "context": {
        "flow": "DataProcessor",
        "step": "ReadInputFile",
        "user": "System"
    }
}
```

### 2. Error Categories
1. System Errors
   - File system
   - Network
   - Memory
   - Permissions

2. Application Errors
   - UI automation
   - Data processing
   - Business logic
   - Validation

3. User Errors
   - Invalid input
   - Missing data
   - Wrong format
   - Unauthorized access