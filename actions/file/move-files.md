# Move File(s)

## Description
Move one or more files into a destination folder.

## Syntax
```
File.Move Files: `[file(s) to move]` Destination: `[destination folder]` IfFileExists: File.IfExists.DoNothing MovedFiles=> MovedFiles
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| File(s) to move | Yes | List of Files | - | The file(s) to move. This value can be a file path, or a variable containing a file, a list of files, a textual path, or a list of text paths |
| Destination folder | Yes | Folder | - | The destination folder for the moved files |
| If file exists | No | Do nothing, Overwrite | Do nothing | Specifies what to do if a file with the same name already exists in the destination folder |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| MovedFiles | List of Files | The moved file(s) as a list of files |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Source folder doesn't exist | Indicates that the source folder doesn't exist |
| Destination folder doesn't exist | Indicates that the destination folder doesn't exist |
| File not found | Indicates that the file doesn't exist |
| Can't move file | Indicates a problem moving the file |