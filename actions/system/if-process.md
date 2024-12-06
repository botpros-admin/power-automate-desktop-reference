# If Process

## Description
Marks the beginning of a conditional block of actions depending on whether a process is running or not.

## Syntax
```
IF (System.IfProcess.ProcessIsRunning ProcessName: `[process name]`) THEN
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| If process | Yes | Is running, Isn't running | Is running | State of the process to check |
| Process name | Yes | Text value | - | The name of the process to check |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Can't retrieve list of processes | Indicates a problem retrieving the list of processes |