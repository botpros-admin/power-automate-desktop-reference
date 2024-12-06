# Rename File(s)

## Description
Change the name of one or more files.

## Syntax
```
File.RenameFiles.Rename Files: `[file(s) to rename]` NewName: `[new name]` KeepExtension: True IfFileExists: File.IfExists.DoNothing RenamedFiles=> RenamedFiles
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| File to rename | Yes | List of Files | - | The file(s) to rename. This value can be a file path, or a variable containing a file, a list of files, a text path, or a list of text paths |
| Add number to | No | Boolean value | True | Specifies whether to add the number to the existing file name(s) or a new name |
| Rename scheme | Yes | Set new name, Add text, Remove text, Replace text, Change extension, Add datetime, Make sequential | Set new name | Specifies how to rename the file(s) |
| New file name | Yes | Text value | - | The new name of the file(s) |
| Keep extension | No | Boolean value | True | Specifies whether to include the previous extension with the file name(s) |
| If file exists | No | Do nothing, Overwrite | Do nothing | Specifies what to do if a file with the same name already exists in the folder |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| RenamedFiles | List of Files | The renamed file(s) as a list of files |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Directory not found | Indicates that the directory wasn't found |
| File not found | Indicates that the file doesn't exist |
| Can't rename file | Indicates a problem renaming the file |