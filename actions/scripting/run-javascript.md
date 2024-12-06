# Run JavaScript

## Description
Executes custom JavaScript code and retrieves its output into a variable. This action provides a specialized JavaScript environment configured specifically for Power Automate Desktop (PAD).

## Syntax
```
Scripting.RunJavascript.RunJavascript JavascriptCode: $'''[JavaScript code]''' ScriptOutput=> JavascriptOutput
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| JavaScriptCode | Yes | Text value | - | The JavaScript code to execute. Variables can be included using %VariableName% syntax |
| Fail after timeout | No | Boolean value | - | Whether the JavaScript script will run indefinitely or fail after a set period of time |
| Timeout | Yes (if Fail after timeout is true) | Numeric value | 10 | The maximum number of seconds to wait for the script to complete (-1 for indefinitely) |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| JavascriptOutput | Text value | The script's output. Captures output from WScript.Echo() |
| ScriptError | Text value | The errors that may occur during execution |

## Script Environment

### Variable Access
```javascript
// PAD variables are accessed using %Variable% syntax
var padVariable = '%VariableName%';

// All variables come in as strings by default
var numericVar = parseInt('%NumericVariable%');
var booleanVar = '%BooleanVariable%' === 'true';
```

### Output Method
```javascript
// Use WScript.Echo to return output
WScript.Echo('Output data');
```

### Data Type Handling
```javascript
// Convert string to number
var num = parseInt('%NumericVariable%');
var float = parseFloat('%FloatVariable%');

// Handle boolean values
var bool = '%BooleanVariable%' === 'true';

// Format numbers back to strings
WScript.Echo(num.toString());
```

## Examples

### Basic Variable Operations
```javascript
// Basic variable access
var name = '%UserName%';
WScript.Echo(name);

// String manipulation
var text = '%InputText%';
WScript.Echo(text.toUpperCase());
```

### Numeric Calculations
```javascript
// Parse and calculate
var num1 = parseFloat('%Number1%');
var num2 = parseFloat('%Number2%');
WScript.Echo(num1 + num2);
```

### JSON Processing
```javascript
// Parse and manipulate JSON
var jsonString = '%JsonInput%';
try {
    var data = JSON.parse(jsonString);
    WScript.Echo(JSON.stringify({
        name: data.name,
        count: data.items.length
    }));
} catch (e) {
    WScript.Echo('Error: ' + e.message);
}
```

### Date Handling
```javascript
// Work with dates
var date = new Date('%DateInput%');
WScript.Echo(
    date.getFullYear() + '-' +
    String(date.getMonth() + 1).padStart(2, '0') + '-' +
    String(date.getDate()).padStart(2, '0')
);
```

### Array Processing
```javascript
// Process arrays
var items = '%CSVInput%'.split(',');
var processed = items
    .map(item => item.trim())
    .filter(item => item.length > 0)
    .join(', ');
WScript.Echo(processed);
```

## Best Practices

1. **Variable Access**
   - Always use %VariableName% syntax for PAD variables
   - Convert types explicitly (strings to numbers, etc.)
   - Validate variable existence before use

2. **Output Handling**
   - Use WScript.Echo for all outputs
   - Format complex data as strings before output
   - Include error messages in output when appropriate

3. **Error Handling**
   - Implement try/catch blocks for error handling
   - Validate inputs before processing
   - Return meaningful error messages

4. **Code Organization**
   - Keep scripts focused and single-purpose
   - Use clear variable names
   - Add comments for complex logic

## Common Issues

1. **Variable Issues**
   - Check variable name spelling in %Variable% syntax
   - Verify variables exist in PAD flow
   - Handle missing or empty variables

2. **Type Conversion**
   - Always validate before converting types
   - Handle invalid number formats
   - Check for null/undefined values

3. **Output Formatting**
   - Convert all outputs to strings
   - Format JSON with JSON.stringify
   - Handle circular references in objects