# Move Folder

## Description
Move an existing folder into a destination folder.

## Syntax
```
Folder.Move Folder: `[source folder]` Destination: `[destination folder]` MovedFolder=> MovedFolder
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Folder to move | Yes | Folder | - | Enter or choose the full path of the folder, or a variable containing the folder, to move |
| Destination folder | Yes | Folder | - | Enter or choose the full path of the folder, or a variable containing the folder, to be the destination folder |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| MovedFolder | Folder | The moved folder object (which is a representation and can access the folder and all its information) |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Folder doesn't exist | Indicates that the folder wasn't found |
| Destination folder doesn't exist | Indicates that the destination folder wasn't found |
| Can't move folder | Indicates a problem moving the folder |