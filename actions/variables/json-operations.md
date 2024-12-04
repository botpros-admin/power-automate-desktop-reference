# JSON Operations

## Convert JSON to Custom Object

### Description
Convert a JSON string to a custom object.

### Syntax
```
Variables.ConvertJsonToCustomObject Json: `` CustomObject=> JsonAsCustomObject
```

### Parameters
| Parameter | Required | Accepts | Description |
|-----------|----------|---------|-------------|
| JSON | Yes | Text value | A JSON text to convert to a custom object |

### Output
| Variable | Type | Description |
|----------|------|-------------|
| JsonAsCustomObject | General value | The converted custom object |

### Exceptions
- Error parsing the JSON

## Convert Custom Object to JSON

### Syntax
```
Variables.ConvertCustomObjectToJson CustomObject: `` Json=> CustomObjectAsJson
```

### Parameters
| Parameter | Required | Accepts | Description |
|-----------|----------|---------|-------------|
| Custom object | Yes | Custom object | The custom object to convert to JSON |

### Output
| Variable | Type | Description |
|----------|------|-------------|
| CustomObjectAsJson | Text value | The converted JSON string |