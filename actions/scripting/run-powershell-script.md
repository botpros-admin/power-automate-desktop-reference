# Run PowerShell Script

## Description
Executes custom PowerShell script and retrieves its output into a variable.

## Syntax
```
Scripting.RunPowershellScript.RunPowershellScript Script: $'''''' ScriptOutput=> PowershellOutput
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| PowerShell code to run | Yes | Text value | - | The PowerShell code to execute |
| Fail after timeout | No | Boolean value | - | Whether the PowerShell script will run indefinitely or fail after a set period of time |
| Timeout | Yes (if Fail after timeout is true) | Numeric value | 10 | The maximum number of seconds to wait for the script to complete (-1 for indefinitely) |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| PowershellOutput | Text value | The script's output |
| ScriptError | Text value | The errors that may occur during execution |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to run PowerShell script | Indicates a problem running the provided PowerShell script |
| Failed to run script in the allotted time | Indicates a problem running the provided script in the allotted time |

## Example Usage

```powershell
# Get system information
Scripting.RunPowershellScript.RunPowershellScript Script: $'''Get-ComputerInfo''' ScriptOutput=> SystemInfo

# Execute complex script
Scripting.RunPowershellScript.RunPowershellScript Script: $'''
$processes = Get-Process
foreach ($p in $processes) {
    if ($p.CPU -gt 50) {
        Write-Output "High CPU: $($p.Name)"
    }
}
''' ScriptOutput=> HighCPUProcesses
```

## Best Practices
1. Use proper error handling in PowerShell scripts
2. Consider script execution policy requirements
3. Handle sensitive data appropriately
4. Use appropriate timeouts for long-running scripts
5. Format output for easy parsing