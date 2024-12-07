# Sort and Filter Data Table

## Description
Provides methods to sort and filter data table contents.

## Sort Data Table

### Syntax
```
Variables.SortDataTable.SortWithColumnName DataTable: `[table]` ColumnName: `[column]` Order: Variables.SortDirection.Ascending
```

### Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Data table | Yes | Datatable | - | Table to sort |
| Specify column with | Yes | Name, Index | Name | How to identify column |
| Column name | Yes (if by name) | Text value | - | Column to sort by |
| Column index | Yes (if by index) | Numeric value | - | Column index to sort by |
| Order | Yes | Ascending, Descending | Ascending | Sort direction |

### Exceptions
| Exception | Description |
|-----------|-------------|
| Column not found | Column name missing |
| Invalid index | Column index invalid |
| Type mismatch | Different types in column |

## Filter Data Table

### Syntax
```
Variables.FilterDataTable DataTable: `[table]` FilterParameters: `[filters]` FilteredDataTable=> FilteredDataTable
```

### Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Data table | Yes | Datatable | - | Table to filter |
| Filters to apply | Yes | Filtering rules | - | Filter conditions |

### Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| FilteredDataTable | Datatable | Filtered results |

### Exceptions

| Exception | Description |
|-----------|-------------|
| Column not found | Column missing |
| Invalid index | Index out of range |
| Type mismatch | Different types in column |