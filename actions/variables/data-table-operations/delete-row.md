# Delete Row from Data Table

## Description
Delete a data table row at the corresponding row index.

## Syntax
```
Variables.DeleteRowFromDataTable DataTable: `[table]` RowIndex: `[index]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Data table | Yes | Datatable | - | The data table to modify |
| Row index | Yes | Numeric value | - | The row index to delete |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Item index is out of range | Specified data table item is out of range |