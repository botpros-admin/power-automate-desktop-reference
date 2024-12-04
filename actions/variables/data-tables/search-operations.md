# Data Table Search and Filter Operations

## Overview
Comprehensive guide to searching, filtering, and analyzing data tables.

## Search Operations

### Find Value
```powershell
Variables.FindOrReplaceInDataTable.FindItemInDataTableEverywhere 
    DataTable: %MyTable% 
    AllMatches: True 
    ValueToFind: "SearchText" 
    MatchCase: False 
    MatchEntireCellContents: False 
    DataTableMatches=> SearchResults
```

### Find and Replace
```powershell
Variables.FindOrReplaceInDataTable.FindAndReplaceEverywhere 
    DataTable: %MyTable% 
    AllMatches: True 
    ValueToFind: "OldText" 
    ValueToReplace: "NewText" 
    MatchCase: False
```

## Filter Operations

### Basic Filter
```powershell
Variables.FilterDataTable 
    DataTable: %MyTable% 
    FilterParameters: {
        "Column": "Age",
        "Operator": "GreaterThan",
        "Value": 18
    } 
    FilteredDataTable=> AdultCustomers
```

### Complex Filter
```powershell
Variables.FilterDataTable 
    DataTable: %MyTable% 
    FilterParameters: {
        "Conditions": [
            {
                "Column": "Age",
                "Operator": "GreaterThan",
                "Value": 18
            },
            {
                "Column": "Status",
                "Operator": "Equals",
                "Value": "Active"
            }
        ],
        "LogicalOperator": "AND"
    } 
    FilteredDataTable=> ActiveAdultCustomers
```

## Sort Operations

### Basic Sort
```powershell
Variables.SortDataTable.SortWithColumnName 
    DataTable: %MyTable% 
    ColumnName: "LastName" 
    Order: Variables.SortDirection.Ascending
```

### Multi-Column Sort
```powershell
Variables.SortDataTable.SortWithMultipleColumns 
    DataTable: %MyTable% 
    SortParameters: [
        {
            "Column": "LastName",
            "Direction": "Ascending"
        },
        {
            "Column": "FirstName",
            "Direction": "Ascending"
        }
    ]
```

## Analysis Operations

### Group By
```powershell
Variables.GroupDataTable 
    DataTable: %SalesTable% 
    GroupByColumn: "Region" 
    AggregateColumns: [
        {
            "Column": "Sales",
            "Function": "Sum"
        },
        {
            "Column": "Orders",
            "Function": "Count"
        }
    ] 
    GroupedTable=> SalesByRegion
```

### Pivot
```powershell
Variables.PivotDataTable 
    DataTable: %SalesTable% 
    RowField: "Product" 
    ColumnField: "Region" 
    ValueField: "Sales" 
    AggregateFunction: "Sum" 
    PivotTable=> ProductSalesByRegion
```