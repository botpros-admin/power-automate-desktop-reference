# Insert Column into Data Table

## Description
Inserts a column at the end or before a specific index value.

## Syntax
```
Variables.AddColumnToDataTable.AppendColumnToDataTable DataTable: `[table]` ColumnName: `[name]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Data table | Yes | Datatable | - | The data table to modify |
| Into location | Yes | End of data table, Before column index | End of data table | Where to insert column |
| Column name | Yes | Text value | - | Name for new column |
| Column index | Yes (if before index) | Numeric value | - | Index to insert before |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Column index out of range | Index is invalid |
| Duplicate column name | Name already exists |