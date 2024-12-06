# Rename Folder

## Description
Change the name of a folder.

## Syntax
```
Folder.Rename Folder: `[folder path]` NewName: `[new name]` RenamedFolder=> RenamedFolder
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Folder to rename | Yes | Folder | - | Enter or choose the full path of the folder, or a variable containing the folder, to change its name |
| New folder name | Yes | Text value | - | Enter the text, or a text variable, to be the new folder name |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| RenamedFolder | Folder | The renamed folder object (which is a representation and can access the folder and all its information) |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Folder doesn't exist | Indicates that the folder wasn't found |
| Can't rename folder | Indicates a problem renaming the folder |