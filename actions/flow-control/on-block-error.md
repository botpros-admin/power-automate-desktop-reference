# On Block Error

## Description
Marks the beginning of a block to handle actions errors.

## Syntax
```
BLOCK 
ON BLOCK ERROR
THROW ERROR
END
END
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Name | No | Text value | - | The name of the Exception Block for Visual purposes only |
| Capture unexpected logic errors | No | Boolean | False | Expand the scope of error handling, also capturing logical errors in the flow |

## Example Usage

```powershell
# Basic error handling
BLOCK "File Operations"
ON BLOCK ERROR
    # Error handling actions
    Variables.SetVariable ErrorMessage: %LastError%
    System.ShowMessageDialog Message: "Error occurred: %ErrorMessage%"
THROW ERROR
END

# Main actions
File.ReadTextFromFile File: "input.txt" Content=> FileContents
END

# Advanced error handling with logic errors
BLOCK "Calculation Block"
ON BLOCK ERROR CaptureLogicErrors: True
    Variables.SetVariable ErrorDetails: %LastError%
    System.LogMessage "Error in calculation: %ErrorDetails%"
THROW ERROR
END

# Main calculation actions
Variables.Calculate Result: 100 / UserInput
END
```

## Best Practices
1. Use meaningful block names
2. Consider scope of error handling
3. Log error details appropriately
4. Handle errors at appropriate levels
5. Clean up resources in error handlers