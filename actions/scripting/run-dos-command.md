# Run DOS Command

## Description
Executes a DOS command or console application in invisible mode and retrieves its output upon completion.

## Syntax
```
Scripting.RunDOSCommand.RunDOSCommand DOSCommandOrApplication: `` StandardOutput=> CommandOutput StandardError=> CommandErrorOutput ExitCode=> CommandExitCode
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| DOS command or application | Yes | File | - | The name of DOS command or a console application, with arguments if applicable |
| Working folder | No | Folder | - | The full path of the folder to work out of, if applicable |
| Fail after timeout | No | Boolean value | - | Whether the DOS command or application will run indefinitely or fail after a set period of time |
| Timeout | Yes (if Fail after timeout is true) | Numeric value | 10 | The maximum number of seconds to wait for the script to complete (-1 for indefinitely) |
| Change code page | No | Boolean value | False | Whether to change the session's current code page |
| Encoding | Yes (if Change code page is true) | [List of encodings] | utf-8 | The encoding to use when reading the output |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CommandOutput | Text value | The text output from the DOS command or application |
| CommandErrorOutput | Text value | The text describing the errors occurred (if any) during execution |
| CommandExitCode | Numeric value | The command or application exit code |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Can't execute command or console application | Indicates a problem executing the specified command or console application |
| Failed to run script in the allotted time | Indicates a problem running the provided script in the allotted time |

## Example Usage

```powershell
# List directory contents
Scripting.RunDOSCommand.RunDOSCommand DOSCommandOrApplication: "dir /w" StandardOutput=> DirOutput StandardError=> DirError ExitCode=> DirExitCode

# Execute a batch file
Scripting.RunDOSCommand.RunDOSCommand DOSCommandOrApplication: "C:\Scripts\process.bat" StandardOutput=> BatchOutput StandardError=> BatchError ExitCode=> BatchExitCode
```

## Best Practices
1. Always check the ExitCode to verify successful execution
2. Use appropriate timeouts for long-running commands
3. Consider encoding when dealing with non-ASCII output
4. Handle both StandardOutput and StandardError
5. Use explicit working folders when working with relative paths