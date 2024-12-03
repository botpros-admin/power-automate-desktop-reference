# Run PowerShell Script Action

## Description
Executes custom PowerShell script and retrieves its output.

## Syntax
```
Scripting.RunPowershellScript.RunPowershellScript Script: $'''''' ScriptOutput=> PowershellOutput
```

## Parameters
- Script (Required): The PowerShell code to execute

## Output Variables
- PowershellOutput: The script's output
- ScriptError: The errors that may occur during execution

## Examples
```powershell
# Get system information
Scripting.RunPowershellScript.RunPowershellScript Script: $'''Get-ComputerInfo''' ScriptOutput=> SystemInfo

# List running processes
Scripting.RunPowershellScript.RunPowershellScript Script: $'''Get-Process | Select-Object Name, CPU''' ScriptOutput=> ProcessList
```

## Exceptions
- Failed to run PowerShell script
- Failed to run script in the allotted time