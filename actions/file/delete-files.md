# Delete File(s)

## Description
Delete one or more files.

## Syntax
```
File.Delete Files: `[file(s) to delete]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| File(s) to delete | Yes | List of Files | - | The file(s) to delete. This value can be a file path, or a variable containing a file, a list of files, a text path, or a list of text paths |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| File path doesn't exist | Indicates that the file path doesn't exist |
| File not found | Indicates that the file doesn't exist |
| Can't delete file | Indicates a problem deleting the file |