# Run Subflow

## Description
Run a subflow specifying any required arguments.

## Syntax
```
CALL FUNCTION `[subflow name]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Subflow name | Yes | Subflow | - | The name of the subflow to call |
| Input as expression | No | Boolean value | False | Define whether the input should be handled as an expression. If enabled, variables and expressions can be used to dynamically determine the subflow during runtime |

## Output Variables
This action doesn't produce any variables.

## Exceptions
This action doesn't include any exceptions.