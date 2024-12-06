# Create Folder

## Description
Create a new folder.

## Syntax
```
Folder.Create FolderPath: `[folder path]` FolderName: `[name]` Folder=> NewFolder
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Create new folder into | Yes | Folder | - | Enter or choose the full path of the folder, or a variable containing the folder, to create a new folder in |
| New folder name | Yes | Text value | - | Enter the text, or a text variable, to be the name of the new folder |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| NewFolder | Folder | The created folder object (which is a representation and can access the folder and all its information) |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Folder doesn't exist | Indicates that the folder wasn't found |
| Can't create folder | Indicates a problem creating the folder |
| New folder path and name are empty | Indicates that both the new folder path and folder name don't have value |