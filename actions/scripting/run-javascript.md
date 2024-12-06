# Run JavaScript

## Description
Executes custom JavaScript code and retrieves its output into a variable. This action supports interaction with PAD variables, string manipulation, mathematical operations, error handling, and various other JavaScript functionalities.

## Syntax
```
Scripting.RunJavascript.RunJavascript JavascriptCode: $'''[JavaScript code]''' ScriptOutput=> JavascriptOutput
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| JavaScriptCode | Yes | Text value | - | The JavaScript code to execute. Can include PAD variables using %VariableName% syntax |
| Fail after timeout | No | Boolean value | - | Whether the JavaScript script will run indefinitely or fail after a set period of time |
| Timeout | Yes (if Fail after timeout is true) | Numeric value | 10 | The maximum number of seconds to wait for the script to complete (-1 for indefinitely) |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| JavascriptOutput | Text value | The script's output, captured from WScript.StdOut.Write calls |
| ScriptError | Text value | The errors that may occur during execution |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to run script in the allotted time | Indicates a problem running the provided script in the allotted time |

## Key Features

1. **Variable Access**
   - Access PAD variables using %VariableName% syntax
   - All variables are passed as strings by default
   - Requires explicit type conversion for numbers and other types

2. **Output Methods**
   - Use WScript.StdOut.Write() for output
   - Multiple writes are concatenated in the output
   - Supports \n for line breaks

3. **Error Handling**
   - Supports try/catch blocks
   - Can capture and report specific error messages
   - Errors are accessible via ScriptError variable

## Example Usage

### Basic Variable Manipulation
```javascript
// Access and modify PAD variables
var name = '%UserName%';
name = name.toUpperCase();
WScript.StdOut.Write(name);
```

### String Operations
```javascript
// Replace and transform text
var text = '%InputText%';
text = text.replace(/-/g, "").replace(/O/g, "0");
WScript.StdOut.Write(text);

// Concatenate strings
var firstName = '%FirstName%';
var lastName = '%LastName%';
WScript.StdOut.Write(firstName + " " + lastName);
```

### Numeric Operations
```javascript
// Parse and calculate
var num1 = parseFloat('%Number1%');
var num2 = parseFloat('%Number2%');
WScript.StdOut.Write(num1 + num2);

// Generate random numbers
var random = Math.floor(Math.random() * 100) + 1;
WScript.StdOut.Write(random);
```

### Conditional Logic
```javascript
// Check conditions
var status = '%Status%';
if (status === "Active") {
    WScript.StdOut.Write("Active user");
} else {
    WScript.StdOut.Write("Inactive user");
}
```

### Array Operations
```javascript
// Process comma-separated values
var items = '%ItemList%'.split(',');
for (var i = 0; i < items.length; i++) {
    WScript.StdOut.Write(items[i] + "\n");
}
```

### Error Handling
```javascript
// Handle potential errors
try {
    var value = '%InputValue%';
    var result = parseInt(value) * 10;
    WScript.StdOut.Write(result);
} catch (e) {
    WScript.StdOut.Write("Error: " + e.message);
}
```

### Date Operations
```javascript
// Calculate date differences
var startDate = new Date('%StartDate%');
var endDate = new Date('%EndDate%');
var days = (endDate - startDate) / (1000 * 60 * 60 * 24);
WScript.StdOut.Write(days);
```

### JSON Handling
```javascript
// Parse and access JSON
var jsonStr = '%JsonData%';
var jsonObj = JSON.parse(jsonStr);
WScript.StdOut.Write(jsonObj.propertyName);
```

## Best Practices
1. Always use WScript.StdOut.Write for output
2. Convert variable types explicitly (parseFloat, parseInt, etc.)
3. Implement error handling with try/catch blocks
4. Use appropriate string methods for text manipulation
5. Format output clearly with line breaks when needed
6. Comment code for clarity
7. Validate input data before processing
8. Handle edge cases and null values

## Common Patterns

### Input Validation
```javascript
var input = '%InputValue%';
if (!input || input.trim() === '') {
    WScript.StdOut.Write('Invalid input');
    return;
}
```

### Multiple Line Output
```javascript
var result = [];
result.push('Line 1');
result.push('Line 2');
result.push('Line 3');
WScript.StdOut.Write(result.join('\n'));
```

### Data Transformation
```javascript
var data = '%RawData%';
var transformed = data
    .split(',')
    .map(item => item.trim())
    .filter(item => item.length > 0)
    .join(', ');
WScript.StdOut.Write(transformed);
```