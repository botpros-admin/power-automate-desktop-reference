# Get Files in Folder

## Description
Retrieve the list of files in a folder.

## Syntax
```
Folder.GetFiles Folder: `` FileFilter: $'''*''' IncludeSubfolders: False FailOnAccessDenied: True SortBy1: Folder.SortBy.NoSort SortDescending1: False SortBy2: Folder.SortBy.NoSort SortDescending2: False SortBy3: Folder.SortBy.NoSort SortDescending3: False Files=> Files
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Folder | Yes | Folder | - | Full path of the folder to retrieve files from |
| File filter | No | Text value | * | Filter to limit files retrieved (e.g., *.txt; *.doc) |
| Include subfolders | No | Boolean | False | Whether to look into subfolders |
| Fail upon denied access | No | Boolean | True | Whether to throw error on access denied |
| Sort by | No | Enum | NoSort | First sort criterion |
| Descending | No | Boolean | False | Sort order for first criterion |
| Then by | No | Enum | NoSort | Second sort criterion |
| Descending | No | Boolean | False | Sort order for second criterion |
| Then by | No | Enum | NoSort | Third sort criterion |
| Descending | No | Boolean | False | Sort order for third criterion |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| Files | List of Files | Retrieved files as list of file objects |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Folder doesn't exist | Target folder not found |
| Can't retrieve list of files | Problem retrieving file list |

## Example Usage

```powershell
# Get all text files
Folder.GetFiles Folder: "C:\Documents" FileFilter: $'''*.txt''' IncludeSubfolders: True FailOnAccessDenied: True Files=> TextFiles

# Get files sorted by date
Folder.GetFiles Folder: "C:\Downloads" SortBy1: Folder.SortBy.LastModified SortDescending1: True Files=> RecentFiles
```

## Best Practices
1. Use specific file filters when possible
2. Handle access denied scenarios
3. Consider memory usage with large folders
4. Use appropriate sorting for performance
5. Clean up file lists when done