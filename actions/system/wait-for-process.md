# Wait for Process

## Description
Suspends the execution until a process starts or stops.

## Syntax
```
WAIT (System.WaitForProcess.ProcessToStart ProcessName: `[process name]`)
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Process name | Yes | Text value | - | The name of the process to check |
| Wait for process to | Yes | Start, Stop | Start | Whether to wait until a certain process starts or stops |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Can't retrieve list of processes | Indicates a problem retrieving the list of processes |