# Get Windows Environment Variable

## Description
Retrieves the value of an environment variable.

## Syntax
```
System.GetEnvironmentVariable.GetEnvironmentVariable Name: `[variable name]` Value=> EnvironmentVariableValue
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Environment variable name | Yes | Text value | - | The name of the environment variable whose value will be retrieved |
| Search for variable only in scope | No | Boolean value | False | Specify whether to search for the variable only in a specific scope |
| Scope | Yes (if searching in scope) | User, System | User | The scope from which the environment variable should be retrieved |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| EnvironmentVariableValue | Text value | The environment variable's value |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Environment variable doesn't exist | Indicates that the specified environment variable doesn't exist |
| Insufficient permissions | Indicates that the user has insufficient permissions to perform this action |