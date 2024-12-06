# Set Windows Environment Variable

## Description
Sets an environment variable to a given value.

## Syntax
```
System.SetEnvironmentVariable Name: `[variable name]` Value: `[value]` Type: System.EnvironmentVariableType.User
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Environment variable name | Yes | Text value | - | The name of the environment variable |
| New environment variable value | Yes | Text value | - | The value that is set to the environment variable |
| Type | Yes | User, System | User | The type of the environment variable |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Indicates a problem setting the environment variable's value | Indicates a problem setting the environment variable's value |
| Insufficient permissions | Indicates that the user has insufficient permissions to perform this action |