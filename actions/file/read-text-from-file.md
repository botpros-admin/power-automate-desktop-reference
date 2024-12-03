# Read Text From File Action

## Description
Read the contents of a text file.

## Syntax
```
File.ReadTextFromFile.ReadText File: `` Encoding: File.TextFileEncoding.UTF8 Content=> FileContents
```

## Parameters
- File (Required): The file to read
- Encoding: System default, ASCII, Unicode, UTF-8 (Default: UTF-8)
- Store content as: Single text value or List (Default: Single text value)

## Output Variables
- FileContents: The contents as text or list of texts

## Examples
```powershell
# Read a text file as single value
File.ReadTextFromFile.ReadText File: "C:\Logs\app.log" Encoding: File.TextFileEncoding.UTF8 Content=> LogContent

# Read file as list of lines
File.ReadTextFromFile.ReadLines File: "C:\Data\users.txt" Encoding: File.TextFileEncoding.UTF8 Content=> UserList
```

## Exceptions
- Directory not found
- File not found
- Failed to read from file