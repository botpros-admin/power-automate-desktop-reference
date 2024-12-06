# Wait for File

## Description
Suspend the execution of the automation until a file is created or deleted.

## Syntax
```
WAIT (File.WaitForFile.Created File: `[file path]`)
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Wait for file to be | Yes | Created, Deleted | Created | Specifies whether to pause the flow on the creation or deletion of a certain file |
| File path | Yes | File | - | The full path to look for the file |

## Output Variables
This action doesn't produce any variables.

## Exceptions
This action doesn't include any exceptions.