# Update Data Table Item

## Description
Update a data table row item on a defined column.

## Syntax
```
Variables.ModifyDataTableItem DataTable: `[table]` ColumnNameOrIndex: `[column]` RowIndex: `[row]` Value: `[value]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Data table | Yes | Datatable | - | The data table to modify |
| Column | Yes | Text value | - | Column name or index to update |
| Row | Yes | Numeric value | - | Row index to update |
| New value | Yes | Text value | - | Value to set in the cell |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Item index is out of range | Row index is invalid |
| Column name doesn't exist | Column name not found |
| Column index is out of range | Column index invalid |
| Incompatible type error | Input has wrong type |