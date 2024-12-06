# Delete Windows Environment Variable

## Description
Deletes an environment variable from a given scope.

## Syntax
```
System.DeleteEnvironmentVariable Name: `[variable name]` Type: System.EnvironmentVariableType.User
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Environment variable name | Yes | Text value | - | The name of the environment variable to delete |
| Type | Yes | User, System | User | The type of the environment variable to delete |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to delete environment variable | Indicates a problem deleting an environment variable |
| Insufficient permissions | Indicates that the user has insufficient permissions to perform this action |