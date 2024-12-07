# Create Directories Subflow Example

## Description
A subflow that creates necessary project directories and handles PDF invoices.

## Complete Code

```
FUNCTION 'Create Necessary directories' GLOBAL
    **REGION Retrieve Project Name
    # Get Documents folder path and clean up any previous files
    Folder.GetSpecialFolder SpecialFolder: Folder.SpecialFolder.Personal SpecialFolderPath=> DocFolderPath
    File.Delete Files: $'''%DocFolderPath%\SanitizedTitleOutput_UTF8.txt'''
    ON ERROR FileNotFoundError
    END

    # Extract project name using PowerShell
    @@copilotGeneratedAction: 'False'
    Scripting.RunPowershellScript.RunPowershellScript Script: $'''[PowerShell script]''' ScriptOutput=> PowershellOutput

    # Save with UTF-8 encoding
    @@copilotGeneratedAction: 'False'
    Scripting.RunPowershellScript.RunPowershellScript Script: $'''[PowerShell script]''' ScriptOutput=> ProjectName

    # Read and clean project name
    File.ReadTextFromFile.ReadText File: $'''%DocFolderPath%\SanitizedTitleOutput_UTF8.txt''' Encoding: File.TextFileEncoding.UTF8 Content=> FileContents
    Text.Trim Text: FileContents TrimOption: Text.TrimOption.Both TrimmedText=> FileContents
    File.Delete Files: $'''%DocFolderPath%\SanitizedTitleOutput_UTF8.txt'''
    **ENDREGION

    **REGION Create Project Folders
    # Create main Power Automate folder if needed
    IF (Folder.IfFolderExists.DoesNotExist Path: $'''%DocFolderPath%\Power Automate''') THEN
        Folder.Create FolderPath: DocFolderPath FolderName: $'''Power Automate'''
    END

    # Create project-specific folder if needed
    IF (Folder.IfFolderExists.DoesNotExist Path: $'''%DocFolderPath%\Power Automate\%FileContents%''') THEN
        # Use PowerShell to handle special characters in folder name
        @@copilotGeneratedAction: 'False'
        Scripting.RunPowershellScript.RunPowershellScript Script: $'''[PowerShell script]''' ScriptOutput=> PowershellOutput
    END
    **ENDREGION

    SET filePath TO $'''%DocFolderPath%\Power Automate\%FileContents%'''

    **REGION Additional Folders
    # Create standard subfolders
    IF (Folder.IfFolderExists.DoesNotExist Path: $'''%filePath%\Scripts''') THEN
        Folder.Create FolderPath: filePath FolderName: $'''Scripts'''
    END
    IF (Folder.IfFolderExists.DoesNotExist Path: $'''%filePath%\Invoices''') THEN
        Folder.Create FolderPath: filePath FolderName: $'''Invoices'''
    END
    IF (Folder.IfFolderExists.DoesNotExist Path: $'''%filePath%\Invoices\Completed''') THEN
        Folder.Create FolderPath: $'''%filePath%\Invoices''' FolderName: $'''Completed'''
    END
    **ENDREGION
END FUNCTION
```

## Structure

1. **Region Organization**
   - Retrieve Project Name
   - Create Project Folders
   - Additional Folders

2. **Error Handling**
   - ON ERROR blocks for file operations
   - Safe folder creation checks

3. **Comments**
   - Brief, descriptive comments for each section
   - Clear explanation of operations

4. **Best Practices**
   - Uses UTF-8 encoding for file operations
   - Handles special characters in folder names
   - Proper cleanup of temporary files

## Control Repository Components
When this example includes UI automation, relevant control repository information should be added at the end of the file in a controlled section:

```
# [ControlRepository][PowerAutomateDesktop]
{...control repository JSON...}
```