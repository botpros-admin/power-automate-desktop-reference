# Terminate Process

## Description
Immediately stops a running process.

## Syntax
```
System.TerminateProcess.TerminateProcessByName ProcessName: `[process name]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Specify process by | Yes | Process ID, Process name | Process name | Specify whether the process to terminate will be specified by its name, or by its ID |
| Process ID | Yes (if by ID) | Numeric value | - | The ID of the process to terminate |
| Process name | Yes (if by name) | Text value | - | The name of the process to terminate. If more than one process with the same name is running, all of them will be terminated |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Process with specified ID not running | Indicates that a process with the specified ID isn't running |
| Failed to terminate process | Indicates a problem terminating the process |