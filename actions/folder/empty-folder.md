# Empty Folder

## Description
Delete all the contents of a folder (files and subfolders) without deleting the folder itself.

## Syntax
```
Folder.Empty Folder: `[folder path]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Folder to empty | Yes | Folder | - | Enter or choose the full path of the folder, or a variable containing the folder, to delete its contents |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Folder doesn't exist | Indicates that the folder wasn't found |
| Can't delete folder's contents | Indicates a problem clearing the folder's contents |