# Get Subfolders in Folder

## Description
Retrieve the list of subfolders in a folder.

## Syntax
```
Folder.GetSubfolders Folder: `[folder path]` FolderFilter: $'''*''' IncludeSubfolders: False FailOnAccessDenied: True SortBy1: Folder.SortBy.NoSort SortDescending1: False SortBy2: Folder.SortBy.NoSort SortDescending2: False SortBy3: Folder.SortBy.NoSort SortDescending3: False Subfolders=> Folders
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Folder | Yes | Folder | - | Enter or choose the full path of the folder, or a variable containing the folder, to retrieve the list of subfolders from |
| Folder filter | Yes | Text value | * | Choose a filter to limit the subfolders retrieved. This parameter allows wild cards, for example, Doc* or Document?. To allow for multiple folder filters, separate the choices with a semi-colon, for example, Doc*;*. |
| Include subfolders | No | Boolean value | False | Specify whether to look into the subfolders and retrieve their subfolders (and so on) as well |
| Fail upon denied access to any subfolder | No | Boolean value | True | Specify whether to throw an error when trying to get subfolders of a folder with no access rights or ignore those folders |
| Sort by | No | No sort, Full name, Root path, Directory, Name, Name without extension, Extension, Size, Creation time, Last accessed, Last modified, Is hidden, Is system, Is read-only, Is archive, Exists | No sort | Specify whether to sort the results and by which criterion |
| Descending | No | Boolean value | False | Specify whether to sort the items in descending or ascending order |
| Then by | No | [Same as Sort by] | No sort | Specify whether to sort the results by a second criterion |
| Descending | No | Boolean value | False | Specify whether to sort the items in descending or ascending order |
| Then by | No | [Same as Sort by] | No sort | Specify whether to sort the results by a third criterion |
| Descending | No | Boolean value | False | Specify whether to sort the items in descending or ascending order |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| Folders | List of Folders | The retrieved subfolders as a list of folder objects |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Folder doesn't exist | Indicates that the folder wasn't found |
| Can't retrieve list of subfolders | Indicates a problem retrieving the list of subfolders |