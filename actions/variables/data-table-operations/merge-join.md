# Merge and Join Data Tables

## Description
Provides methods to combine data tables through merging or joining.

## Merge Data Tables

### Syntax
```
Variables.MergeDataTables FirstDataTable: `[table1]` SecondDataTable: `[table2]` MergeMode: Variables.MergeMode.AddExtraColumns
```

### Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| First data table | Yes | Datatable | - | First table to merge |
| Second data table | Yes | Datatable | - | Second table to merge |
| Merge mode | Yes | Add extra columns, Ignore extra columns, Error on extra columns | Add extra columns | How to handle different columns |

### Exceptions

| Exception | Description |
|-----------|-------------|
| Missing Schema | Tables have different columns |

## Join Data Tables

### Syntax
```
Variables.JoinDataTable FirstDataTable: `[table1]` SecondDataTable: `[table2]` JoinOperation: Variables.JoinOperationType.Inner JoinParameters: `[params]` JoinedDataTable=> JoinedDataTable
```

### Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| First data table | Yes | Datatable | - | First table to join |
| Second data table | Yes | Datatable | - | Second table to join |
| Join operation | Yes | Inner, Left, Full | Inner | Type of join to perform |
| Join rules | Yes | Join rules | - | Join conditions |

### Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| JoinedDataTable | Datatable | Joined result |

### Exceptions

| Exception | Description |
|-----------|-------------|
| Column not found | Column doesn't exist |
| Invalid index | Column index invalid |