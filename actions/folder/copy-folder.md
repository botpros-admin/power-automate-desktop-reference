# Copy Folder

## Description
Copy a folder into a destination folder.

## Syntax
```
Folder.Copy Folder: `[source folder]` Destination: `[destination folder]` IfFolderExists: Folder.IfExists.DoNothing CopiedFolder=> CopiedFolder
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Folder to copy | Yes | Folder | - | Enter or choose the full path of the folder, or a variable containing the folder, to copy. If the folder path ends with a \ only the contents of the folder (files + subfolders) are copied. Otherwise, the folder itself (along with its contents) is copied as a subfolder into the destination folder |
| Destination folder | Yes | Folder | - | Enter or choose the full path of the folder, or a variable containing the folder, to be the destination folder |
| If folder exists | No | Do nothing, Overwrite | Do nothing | Specify whether to overwrite files or not copy them at all, if the destination folder already exists. If the folder exists, but the files have different names, the old files still remain in the folder |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CopiedFolder | Folder | The copied folder object (which is a representation and can access the folder and all its information) |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Folder doesn't exist | Indicates that the folder wasn't found |
| Destination folder doesn't exist | Indicates that the destination folder wasn't found |
| Can't copy folder | Indicates a problem copying the folder |