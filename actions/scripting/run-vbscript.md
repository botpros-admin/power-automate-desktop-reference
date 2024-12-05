# Run VBScript

Executes custom VBScript code and retrieves its output into a variable.

## Syntax

```
Scripting.RunVBScript.RunVBScript VBScriptCode: $'''[VBScript code]''' ScriptOutput=> VBScriptOutput
```

## Parameters

| Parameter | Required | Type | Description |
|-----------|----------|------|-------------|
| VBScriptCode | Yes | Text value | The VBScript code to execute. Variables may be included within the script since they evaluate prior to the execution of the VBScript |
| Fail after timeout | Yes | Boolean value | Specify whether the VBScript script will run indefinitely or fail after a set period of time |
| Timeout | No | Numeric value | The maximum number of seconds to wait for the script to complete (-1 for indefinitely). Default: 10 |

## Returns

| Variable | Type | Description |
|----------|------|-------------|
| VBScriptOutput | Text value | The script's output |
| ScriptError | Text value | The errors that may occur during the execution of the VBScript code |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to run script in the allotted time | Indicates a problem running the provided script in the allotted time |

## Remarks

- You can use this action to include your own custom VBScript code in the desktop flow
- Variables can be included within the script as they are evaluated before execution
- The script's output and any errors are captured in separate variables
- A timeout can be set to prevent infinite execution