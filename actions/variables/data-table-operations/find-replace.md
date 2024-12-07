# Find or Replace in Data Table

## Description
Finds and/or replaces data table values.

## Syntax
```
Variables.FindOrReplaceInDataTable.FindItemInDataTableEverywhere DataTable: `[table]` AllMatches: True ValueToFind: `[search]` MatchCase: False MatchEntireCellContents: False DataTableMatches=> DataTableMatches
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Data table | Yes | Datatable | - | The data table to search |
| Search mode | Yes | Find, Find and replace | Find | Operation mode |
| All matches | No | Boolean value | True | Find all or first match |
| Text to find | Yes | Text value | - | Text to search for |
| Find using regex | No | Boolean value | False | Use regular expression |
| Match case | No | Boolean value | False | Case sensitive search |
| Match entire cell | No | Boolean value | False | Match whole cell only |
| Text to replace | Yes (if replacing) | Text value | - | Replacement text |
| Search by | Yes | Everywhere, On column | Everywhere | Search scope |
| Column | Yes (if by column) | Text value | - | Column to search in |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| DataTableMatches | Datatable | Table with match locations |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Invalid regex | Regular expression is invalid |
| Column not found | Column name not found |
| Column index invalid | Column index out of range |
| Type mismatch | Incompatible type provided |