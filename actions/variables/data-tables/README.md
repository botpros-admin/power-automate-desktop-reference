# Data Table Operations

## Overview
Comprehensive guide to working with Data Tables in Power Automate Desktop.

## Basic Operations

### Create New Data Table
```powershell
Variables.CreateNewDatatable InputTable: { } DataTable=> NewTable
```

### Insert Row
```powershell
Variables.AddRowToDataTable.AppendRowToDataTable DataTable: %ExistingTable% RowToAdd: %NewRow%
```

### Delete Row
```powershell
Variables.DeleteRowFromDataTable DataTable: %ExistingTable% RowIndex: 0
```

## Content Operations

### Update Item
```powershell
Variables.ModifyDataTableItem DataTable: %ExistingTable% ColumnNameOrIndex: "Name" RowIndex: 0 Value: "New Value"
```

### Find and Replace
```powershell
Variables.FindOrReplaceInDataTable.FindItemInDataTableEverywhere DataTable: %ExistingTable% AllMatches: True ValueToFind: "Search Text" MatchCase: False MatchEntireCellContents: False DataTableMatches=> Matches
```

## Column Operations

### Add Column
```powershell
Variables.AddColumnToDataTable.AppendColumnToDataTable DataTable: %ExistingTable% ColumnName: "NewColumn"
```

### Delete Column
```powershell
Variables.DeleteColumnFromDataTable.DeleteColumnWithName DataTable: %ExistingTable% ColumnName: "ColumnToDelete"
```

## Data Table Cleanup

### Delete Empty Rows
```powershell
Variables.DeleteEmptyRowsFromDataTable DataTable: %ExistingTable%
```

### Delete Duplicate Rows
```powershell
Variables.DeleteDuplicateRowsFromDataTable DataTable: %ExistingTable%
```

### Clear Data Table
```powershell
Variables.ClearDataTable DataTable: %ExistingTable%
```

## Best Practices

1. **Initialization**
```powershell
# Create with schema
Variables.CreateNewDatatable InputTable: {
    "Columns": [
        {"Name": "ID", "Type": "Number"},
        {"Name": "Name", "Type": "Text"},
        {"Name": "Email", "Type": "Text"}
    ]
} DataTable=> CustomersTable
```

2. **Data Validation**
```powershell
# Check for empty table
IF DataTable.RowCount(%MyTable%) = 0 THEN
    # Handle empty table
END

# Validate column exists
IF DataTable.HasColumn(%MyTable%, "ColumnName") THEN
    # Process column
END
```

3. **Error Handling**
```powershell
BLOCK "Data Table Operations"
ON BLOCK ERROR
    # Log error
    System.LogMessage "Error processing data table: %LastError%"
    # Cleanup if needed
    Variables.ClearDataTable DataTable: %TempTable%
END
    # Data table operations
END
```