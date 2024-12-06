# Write Text to File

## Description
Write or appends text to a file.

## Syntax
```
File.WriteText File: `[file path]` AppendNewLine: True IfFileExists: File.IfFileExists.Overwrite Encoding: File.FileEncoding.Unicode
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| File path | Yes | File | - | The file to write the text. This value can be a file path, or a variable containing a file or a textual path |
| Text to write | No | General value | - | The text to write in the specified file |
| Append new line | No | Boolean value | True | Specifies whether to append a new line at the end of the overall text to write to the file |
| If file exists | No | Overwrite existing content, Append content | Overwrite existing content | Specifies whether to overwrite the existing content, or to append to the end of the existing content |
| Encoding | No | System default, ASCII, Unicode, Unicode (big-endian), UTF-8, Unicode (without byte order mask), UTF-8 (without byte order mask) | Unicode | The encoding to use for the specified text to write into the text file |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to write text to file | Indicates a problem writing to the file |
| Invalid directory for file | Indicates that the directory is invalid |