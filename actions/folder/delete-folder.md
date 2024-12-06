# Delete Folder

## Description
Delete an existing folder and its contents (files and subfolders).

## Syntax
```
Folder.Delete Folder: `[folder path]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Folder to delete | Yes | Folder | - | Enter or choose the full path of the folder, or a variable containing the folder, to delete. Remember that all contents of that folder and its subfolders are deleted too |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Folder doesn't exist | Indicates that the folder wasn't found |
| Can't delete folder | Indicates a problem deleting the folder |