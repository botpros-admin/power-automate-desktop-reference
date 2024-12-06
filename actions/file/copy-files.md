# Copy File(s)

## Description
Copy one or more files into a destination folder.

## Syntax
```
File.Copy Files: `[file(s) to copy]` Destination: `[destination folder]` IfFileExists: File.IfExists.DoNothing CopiedFiles=> CopiedFiles
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| File(s) to copy | Yes | List of Files | - | The file(s) to copy. This value can be a file path, or a variable containing a file, a list of files, a text path, or a list of text paths |
| Destination folder | Yes | Folder | - | The destination folder for the copied files |
| If file exists | No | Do nothing, Overwrite | Do nothing | Specifies what to do if a file with the same name already exists in the destination folder |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CopiedFiles | List of Files | The copied file(s) as a list of files |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Source folder doesn't exist | Indicates that the source folder doesn't exist |
| Destination folder doesn't exist | Indicates that the destination folder doesn't exist |
| File not found | Indicates that the file doesn't exist |
| Can't copy file | Indicates a problem copying the file |