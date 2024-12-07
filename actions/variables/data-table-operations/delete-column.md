# Delete Column from Data Table

## Description
Delete a data table column at the specified column index or column name.

## Syntax
```
Variables.DeleteColumnFromDataTable.DeleteColumnWithName DataTable: `[table]` ColumnName: `[name]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Data table | Yes | Datatable | - | The data table to modify |
| Specify column with | Yes | Name, Index | Name | How to identify column |
| Column name | Yes (if by name) | Text value | - | Name of column to delete |
| Column index | Yes (if by index) | Numeric value | - | Index of column to delete |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Column not found | Column name doesn't exist |
| Invalid index | Column index out of range |