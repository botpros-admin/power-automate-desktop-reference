# CSV Operations

## Description
Provides methods to convert between CSV format and data tables.

## Read from CSV Text

### Syntax
```
Variables.GenerateDataTableFromCSV.ReadPredefinedSeparator CSVText: `[text]` TrimFields: True FirstLineContainsColumnNames: False ReadFieldsAsText: False ColumnsSeparator: Variables.CSVColumnsSeparator.SystemDefault CSVTable=> CSVTable
```

### Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| CSV text | Yes | Text value | - | CSV text to read |
| Trim fields | No | Boolean value | True | Remove whitespace |
| First line contains column names | No | Boolean value | False | Use first row as headers |
| Get CSV fields as text | No | Boolean value | False | Force text type for all fields |
| Columns separator | Yes | Predefined, Custom, Fixed Column Widths | Predefined | How to split columns |
| Separator | Yes (if predefined) | System default, Comma, Semicolon, Tab | System default | Which separator to use |
| Custom separator | Yes (if custom) | Text value | - | Custom separator character |
| Fixed column widths | Yes (if fixed) | Text value | - | Width of each column |

### Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CSVTable | Datatable | Resulting data table |

### Exceptions

| Exception | Description |
|-----------|-------------|
| CSV parsing failed | Error processing CSV text |

## Convert Data Table to Text

### Syntax
```
Variables.ConvertDataTableToCSV.DataTableToCSVCommonSeparator DataTable: `[table]` IncludeColumnNames: False ColumnsSeparator: Variables.CSVColumnsSeparator.SystemDefault CSVText=> CSVText
```

### Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Data table | Yes | Datatable | - | Table to convert |
| Include column names | No | Boolean value | False | Include headers row |
| Use custom columns separator | No | Boolean value | False | Use custom separator |
| Separator | Yes (if not custom) | System default, Comma, Semicolon, Tab | System default | Which separator to use |
| Custom columns separator | Yes (if custom) | Text value | - | Custom separator character |

### Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CSVText | Text value | Resulting CSV text |

### Exceptions

| Exception | Description |
|-----------|-------------|
| Conversion failed | Error converting to CSV |