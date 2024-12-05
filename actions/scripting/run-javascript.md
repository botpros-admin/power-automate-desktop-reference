# Run JavaScript

Executes custom JavaScript code and retrieves its output into a variable.

## Syntax

```
Scripting.RunJavascript.RunJavascript JavascriptCode: $'''[JavaScript code]''' ScriptOutput=> JavascriptOutput
```

## Parameters

| Parameter | Required | Type | Description |
|-----------|----------|------|-------------|
| JavascriptCode | Yes | Text value | The JavaScript code to execute. Variables may be included within the script since they evaluate prior to the JavaScript code's execution |
| Fail after timeout | Yes | Boolean value | Specify whether the JavaScript script will run indefinitely or fail after a set period of time |
| Timeout | No | Numeric value | The maximum number of seconds to wait for the script to complete (-1 for indefinitely). Default: 10 |

## Returns

| Variable | Type | Description |
|----------|------|-------------|
| JavascriptOutput | Text value | The script's output |
| ScriptError | Text value | The errors that may occur during the execution of the JavaScript code |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to run script in the allotted time | Indicates a problem running the provided script in the allotted time |

## Remarks

- Variables can be included within the script as they are evaluated before the JavaScript code executes
- The script's output and any errors are captured in separate variables
- A timeout can be set to prevent infinite execution