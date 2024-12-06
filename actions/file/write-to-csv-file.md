# Write to CSV File

## Description
Write a data table, data row or list to a CSV file.

## Syntax
```
File.WriteToCSVFile.WriteCSV VariableToWrite: `[variable]` CSVFile: `[file path]` CsvFileEncoding: File.CSVEncoding.UTF8 IncludeColumnNames: False IfFileExists: File.IfFileExists.Overwrite ColumnsSeparator: File.CSVColumnsSeparator.SystemDefault
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Variable to write | Yes | General value | - | The data table, data row variable or list variable to write into the target CSV file |
| File path | Yes | File | - | The CSV file to export the variable to |
| Encoding | No | UTF-8, Unicode, Unicode (big-endian), UTF-8 (No byte order mark), Unicode (no byte order mark), System default, ASCII | UTF-8 | The encoding to use for writing to the specified CSV file |
| Include column names | No | Boolean value | False | Specifies whether the column names should become the first row of the CSV file |
| If file exists | No | Overwrite existing content, Append content | Overwrite existing content | Specifies the desired behavior when the targeted CSV file already exists |
| Separator | No | System default, Comma, Semicolon, Tab | System default | The column separator to use in the specified CSV file |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Write failed | Indicates a problem writing to the CSV file |