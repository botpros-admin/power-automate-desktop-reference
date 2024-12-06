# Read from CSV File

## Description
Read a CSV file into a data table.

## Syntax
```
File.ReadFromCSVFile.ReadCSV CSVFile: `[file path]` Encoding: File.CSVEncoding.UTF8 TrimFields: True FirstLineContainsColumnNames: False ColumnsSeparator: File.CSVColumnsSeparator.SystemDefault CSVTable=> CSVTable
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| File path | Yes | File | - | The CSV file to read |
| Encoding | No | UTF-8, Unicode, Unicode (big-endian), UTF-8 (No byte order mark), Unicode (no byte order mark), System default, ASCII | UTF-8 | The encoding to be used for reading the specified CSV file |
| Trim fields | No | Boolean value | True | Specifies whether to automatically trim off the leading and trailing whitespaces of the extracted cells |
| First line contains column names | No | Boolean value | False | Specifies whether to use the first row of the CSV resource to set the column names |
| Columns separator | No | Predefined, Custom, Fixed column widths | Predefined | Specifies whether to use a predefined columns separator, a custom one or fixed column widths |
| Separator | No (if predefined) | System default, Comma, Semicolon, Tab | System default | The column-separator to parse the CSV file |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| CSVTable | Datatable | The contents of the CSV file as a data table |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Read from CSV failed | Indicates a problem reading from the CSV file |