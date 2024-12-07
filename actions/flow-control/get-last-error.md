# Get Last Error

## Description
Retrieves the last error that occurred in the flow.

## Syntax
```
ERROR => LastError
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Clear error | No | Boolean value | False | After the error is stored in the variable, it's cleared so that next time the error is retrieved, it won't retrieve the same error value |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| LastError | Error | The details of the error that last occurred in the flow |

## Exceptions
This action doesn't include any exceptions.