# Read Text From File

## Description
Read the contents of a text file.

## Syntax
```
File.ReadTextFromFile.ReadText File: `` Encoding: File.TextFileEncoding.UTF8 Content=> FileContents
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| File path | Yes | File | - | The file to read |
| Store content as | Yes | Enum | Single text value | Options: Single text value, List (each line is a list item) |
| Encoding | Yes | Enum | UTF-8 | Options: System default, ASCII, Unicode, Unicode (big-endian), UTF-8 |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| FileContents | Text value or List of Text values | The contents as text or list of texts |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Directory not found | Indicates that the directory wasn't found |
| File not found | Indicates that the file doesn't exist |
| Failed to read from file | Indicates a problem reading from the file |

## Example Usage

```powershell
# Read as single text
File.ReadTextFromFile.ReadText File: "C:\data\input.txt" Encoding: File.TextFileEncoding.UTF8 Content=> FileContents

# Read as list of lines
File.ReadTextFromFile.ReadLines File: "C:\data\input.txt" Encoding: File.TextFileEncoding.UTF8 Lines=> FileLines
```

## Best Practices
1. Always verify file existence before reading
2. Use appropriate encoding for the file content
3. Handle exceptions appropriately
4. Consider memory usage for large files
5. Close files properly after reading