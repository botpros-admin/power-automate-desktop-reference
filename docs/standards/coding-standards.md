# Power Automate Desktop Coding Standards

## 1. Naming Conventions

### Variables
```powershell
# Good examples
Variables.SetVariable CustomerName: "John Doe"
Variables.SetVariable InvoiceTotal: 1250.50
Variables.SetVariable IsProcessComplete: False

# Bad examples
Variables.SetVariable n: "John Doe"          # Too short
Variables.SetVariable var1: 1250.50         # Meaningless name
Variables.SetVariable FLAG: False           # ALL CAPS
```

### Regions
```powershell
# Good examples
REGION "Initialize Variables"
REGION "Process Customer Data"
REGION "Cleanup Resources"

# Bad examples
REGION "Code Block 1"      # Meaningless name
REGION "Do Stuff"          # Vague description
REGION "MAIN PROCESS"      # ALL CAPS
```

## 2. Code Organization

### Flow Structure
```powershell
# Initialize variables
REGION "Initialization"
    Variables.SetVariable Config: {}
    Variables.SetVariable ErrorCount: 0
END REGION

# Main process
REGION "Main Process"
    BLOCK "Process Data"
    ON BLOCK ERROR
        # Error handling
    END
        # Processing logic
    END
END REGION

# Cleanup
REGION "Cleanup"
    # Resource cleanup
END REGION
```

## 3. Error Handling

### Standard Pattern
```powershell
BLOCK "Operation Name"
ON BLOCK ERROR
    # Log error
    System.LogMessage "Error: %LastError%"
    
    # Cleanup
    IF Variables.Exists("TempFile") THEN
        File.Delete Files: %TempFile%
    END
    
    # Notify if needed
    IF ErrorCount > MaxErrors THEN
        Email.SendEmail To: "admin@company.com" Subject: "Flow Error"
    END
END
    # Main operations
END
```

## 4. Comments and Documentation

### Inline Comments
```powershell
# Configuration variables
Variables.SetVariable RetryCount: 3      # Maximum retry attempts
Variables.SetVariable Timeout: 30        # Seconds to wait

# Process each customer record
LOOP FOREACH Customer IN %CustomerList%
    # Skip inactive customers
    IF NOT Customer.IsActive THEN
        NEXT LOOP
    END
    
    # Process customer data
    ProcessCustomerRecord Customer: %Customer%
END LOOP
```

## 5. Variable Management

### Initialization
```powershell
# Initialize all variables at start
REGION "Variable Initialization"
    # Configuration
    Variables.SetVariable Config: {
        "maxRetries": 3,
        "timeout": 30,
        "logPath": "C:\\Logs"
    }
    
    # Counters
    Variables.SetVariable ProcessedCount: 0
    Variables.SetVariable ErrorCount: 0
    
    # Status flags
    Variables.SetVariable IsInitialized: False
    Variables.SetVariable IsProcessing: False
END REGION
```

## 6. UI Automation Standards

### Element Handling
```powershell
# Wait for element with timeout
UI.WaitForElement Element: %LoginButton% Timeout: 30

# Verify element state before action
IF UI.ElementExists(Element: %LoginButton%) AND
   UI.ElementIsEnabled(Element: %LoginButton%) THEN
    UI.ClickElement Element: %LoginButton%
ELSE
    # Handle element not ready
END
```

## 7. File Operation Standards

### File Handling
```powershell
# Check file existence before operations
IF File.Exists(File: %InputFile%) THEN
    # Create backup
    File.Copy Files: %InputFile% Destination: "%InputFile%.bak"
    
    # Process file
    File.ReadTextFromFile File: %InputFile% Content=> FileContent
ELSE
    # Handle missing file
    System.LogMessage "File not found: %InputFile%"
END
```

## 8. Performance Optimization

### Resource Usage
```powershell
# Batch processing
Variables.SetVariable BatchSize: 100
Variables.SetVariable CurrentBatch: []

LOOP FOREACH Item IN %LargeDataset%
    # Add to current batch
    List.AddItem List: %CurrentBatch% Item: %Item%
    
    # Process when batch is full
    IF List.Count(%CurrentBatch%) >= BatchSize THEN
        ProcessBatch Batch: %CurrentBatch%
        Variables.SetVariable CurrentBatch: []
    END
END LOOP
```

## 9. Logging Standards

### Structured Logging
```powershell
# Log entry format
Variables.SetVariable LogEntry: {
    "timestamp": %CurrentDateTime%,
    "level": "INFO",
    "operation": "ProcessCustomer",
    "details": {
        "customerId": %Customer.Id%,
        "status": "Success"
    }
}

# Write to log file
File.WriteText File: "%Config.logPath%\log.txt" Text: %LogEntry%
```