# Data Table Sort and Filter Operations

## Sort Data Table

### Description
Sorts the data table rows in ascending or descending order by the specified column.

### Syntax
```
Variables.SortDataTable.SortWithColumnName DataTable: `` ColumnName: `` Order: Variables.SortDirection.Ascending
```

### Parameters
| Parameter | Required | Accepts | Default | Description |
|-----------|----------|---------|---------|-------------|
| Data table | Yes | Datatable | - | The data table to sort |
| Specify column with | Yes | Enum | Name | Name or Index |
| Column name | Yes* | Text value | - | The name of the column to sort by |
| Column index | Yes* | Numeric | - | The index of the column to sort by |
| Order | Yes | Enum | Ascending | Ascending or Descending |

*One of these is required based on 'Specify column with' selection

### Exceptions
- Column name doesn't exist
- Column index is out of range
- Type mismatch in the cells of a column

## Filter Data Table

### Description
Filters the data table rows based on the applied rules.

### Syntax
```
Variables.FilterDataTable DataTable: `` FilterParameters: `` FilteredDataTable=> FilteredDataTable
```

### Parameters
| Parameter | Required | Accepts | Description |
|-----------|----------|---------|-------------|
| Data table | Yes | Datatable | The data table to filter |
| Filters to apply | Yes | Filtering rules | Complex filter parameters |

### Output
| Variable | Type | Description |
|----------|------|-------------|
| FilteredDataTable | Datatable | The filtered data table |