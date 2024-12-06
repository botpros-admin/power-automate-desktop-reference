# Run VBScript

## Description
Executes custom VBScript code and retrieves its output into a variable.

## Syntax
```
Scripting.RunVBScript.RunVBScript VBScriptCode: $'''''' ScriptOutput=> VBScriptOutput
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| VBScriptCode | Yes | Text value | - | The VBScript code to execute |
| Fail after timeout | No | Boolean value | - | Whether the VBScript will run indefinitely or fail after a set period of time |
| Timeout | Yes (if Fail after timeout is true) | Numeric value | 10 | The maximum number of seconds to wait for the script to complete (-1 for indefinitely) |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| VBScriptOutput | Text value | The script's output |
| ScriptError | Text value | The errors that may occur during execution |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to run script in the allotted time | Indicates a problem running the provided script in the allotted time |

## Example Usage

```vbscript
# Display message box
Scripting.RunVBScript.RunVBScript VBScriptCode: $'''MsgBox "Hello World"''' ScriptOutput=> MessageOutput

# Process text
Scripting.RunVBScript.RunVBScript VBScriptCode: $'''
Dim text
text = "Hello World"
WScript.Echo UCase(text)
''' ScriptOutput=> ProcessedText
```

## Best Practices
1. Use proper error handling
2. Avoid infinite loops
3. Use WScript.Echo for output
4. Set appropriate timeouts
5. Format output for easy parsing