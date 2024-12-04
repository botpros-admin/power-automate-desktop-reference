# Run Application

## Description
Executes an application or opens a document by executing the associated application.

## Syntax
```powershell
System.RunApplication.RunApplication ApplicationPath: `` WindowStyle: System.ProcessWindowStyle.Normal ProcessId=> AppProcessId
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Application path | Yes | File | - | The executable file as a complete file path |
| Command line arguments | No | Text value | - | Extra arguments after executable name |
| Working folder | No | Folder | - | The folder to work from |
| Window style | Yes | Enum | Normal | Normal, Hidden, Minimized, Maximized |
| After application launch | Yes | Enum | Continue immediately | Continue, Wait for load, Wait for complete |
| Timeout | No | Numeric | 0 | Maximum wait time in seconds |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| AppProcessId | Numeric | The process ID output |
| AppExitCode | Numeric | The application exit code |
| WindowHandle | Numeric | The window handle |

## Exceptions

| Exception | Description |
|-----------|-------------|
| File or application not found | Specified file/app not found |
| Access denied | Access denied for app/file |
| Can't get window handle | Problem getting window handle |
| Can't execute application | Problem executing application |

## Example Usage

```powershell
# Simple execution
System.RunApplication.RunApplication 
    ApplicationPath: "notepad.exe" 
    WindowStyle: System.ProcessWindowStyle.Normal 
    ProcessId=> NotePadPID

# With arguments and wait
System.RunApplication.RunAndWait 
    ApplicationPath: "cmd.exe" 
    Arguments: "/c dir" 
    WindowStyle: System.ProcessWindowStyle.Hidden 
    Timeout: 30 
    ProcessId=> CmdPID
```

## Best Practices
1. Always verify application path exists
2. Use appropriate window style
3. Handle timeouts appropriately
4. Check exit codes
5. Clean up processes when done