# System Operations

## Overview
Comprehensive guide to System operations in Power Automate Desktop.

## Categories

### Process Management
1. [If process](./if-process.md)
2. [Wait for process](./wait-for-process.md)
3. [Run application](./run-application.md)
4. [Terminate process](./terminate-process.md)

### Network Operations
1. [Ping](./ping.md)

### Environment Variables
1. [Set Windows environment variable](./set-environment-variable.md)
2. [Get Windows environment variable](./get-environment-variable.md)
3. [Delete Windows environment variable](./delete-environment-variable.md)

## Common Use Cases

### Process Management
```powershell
# Check if process is running
IF System.ProcessIsRunning(ProcessName: "notepad.exe") THEN
    # Process exists
END

# Start process and wait
System.RunApplication.RunAndWait 
    ApplicationPath: "notepad.exe" 
    WindowStyle: System.ProcessWindowStyle.Normal
```

### Environment Variables
```powershell
# Set variable
System.SetEnvironmentVariable 
    Name: "APP_HOME" 
    Value: "C:\Applications" 
    Type: System.EnvironmentVariableType.User

# Get variable
System.GetEnvironmentVariable.GetEnvironmentVariable 
    Name: "APP_HOME" 
    Value=> AppHome
```