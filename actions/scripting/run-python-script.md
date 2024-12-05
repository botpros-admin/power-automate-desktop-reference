# Run Python Script

## Description
Executes Python script code and retrieves its output.

## Syntax
```
Scripting.RunPythonScript PythonCode: '' PythonVersion: System.PythonVersion.Python2 ScriptOutput=> PythonScriptOutput
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| PythonCode | Yes | Text value | - | The Python script code to execute |
| Python version | Yes | Python 2.7, Python 3.4 | Python 2.7 | Version of Python to use when executing the script |
| Module folder paths | No | List of Folders | - | The path(s) of folder(s) where external Python modules lie |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| PythonScriptOutput | Text value | The script's output |
| ScriptError | Text value | The errors that may occur during execution |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to run Python script | Indicates a problem running the provided Python script |
| Directory not found | Indicates that the directory wasn't found |

## Example Usage

```python
# Basic calculation
Scripting.RunPythonScript PythonCode: '''
sum = 0
for i in range(1, 6):
    sum += i
print(f"Sum: {sum}")
''' PythonVersion: System.PythonVersion.Python3 ScriptOutput=> CalcResult

# File processing
Scripting.RunPythonScript PythonCode: '''
import json

data = {
    "name": "John",
    "age": 30
}
print(json.dumps(data, indent=2))
''' PythonVersion: System.PythonVersion.Python3 ScriptOutput=> JsonOutput
```

## Best Practices
1. Specify Python version explicitly
2. Handle module imports properly
3. Use print() for output
4. Consider dependencies
5. Format output for easy parsing