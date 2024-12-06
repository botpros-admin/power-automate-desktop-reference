# Run JavaScript

## Description
Executes custom JavaScript code and retrieves its output into a variable. This action allows for complex data manipulation, calculations, and automation tasks using JavaScript, with full access to Power Automate Desktop variables.

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
| Syntax error in script | Indicates invalid JavaScript syntax in the provided code |
| Variable reference error | Indicates an attempt to access an undefined PAD variable |

## Important Notes

1. **Variable Integration**
   - All PAD variables are accessed using %VariableName% syntax
   - Variables are passed as strings and require explicit type conversion
   - Changes to variables in the script don't affect PAD variables directly

2. **Output Handling**
   - Only WScript.StdOut.Write output is captured
   - Multiple writes are concatenated in order
   - Line breaks require explicit '\n' characters
   - Console.log() is not supported

3. **Performance Considerations**
   - Complex loops should include timeout checks
   - Large data operations should be optimized
   - Memory usage should be monitored in long-running scripts

## Key Features

1. **Variable Access and Manipulation**
   - Access to all PAD flow variables
   - String manipulation capabilities
   - Numeric calculations and conversions
   - Date and time operations

2. **Data Processing**
   - Array and object manipulation
   - JSON parsing and formatting
   - Text processing and validation
   - Regular expression support

3. **Control Flow**
   - Conditional execution
   - Loop constructs
   - Error handling
   - Function definition and usage

## Example Usage

### Basic Variable Operations
```javascript
// Basic variable access and manipulation
var name = '%UserName%';
var age = parseInt('%UserAge%');
WScript.StdOut.Write(`Name: ${name}, Age next year: ${age + 1}`);
```

### String Processing
```javascript
// Advanced string manipulation
var text = '%InputText%';
var processed = text
    .toLowerCase()
    .replace(/[^a-z0-9]/g, '')
    .split('')
    .reverse()
    .join('');
WScript.StdOut.Write(processed);
```

### Data Validation
```javascript
// Input validation with error handling
try {
    var email = '%EmailAddress%';
    var emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    
    if (!email || !emailRegex.test(email)) {
        throw new Error('Invalid email format');
    }
    
    WScript.StdOut.Write('Valid email');
} catch (e) {
    WScript.StdOut.Write('Error: ' + e.message);
}
```

### Complex Data Processing
```javascript
// Process JSON data with error checking
try {
    var jsonData = '%JsonInput%';
    var data = JSON.parse(jsonData);
    
    // Data transformation
    var result = data.items
        .filter(item => item.active)
        .map(item => ({
            id: item.id,
            value: item.value * 1.1
        }));
    
    WScript.StdOut.Write(JSON.stringify(result, null, 2));
} catch (e) {
    WScript.StdOut.Write('Processing error: ' + e.message);
}
```

### Date Calculations
```javascript
// Advanced date manipulation
var startDate = new Date('%StartDate%');
var endDate = new Date('%EndDate%');

var msPerDay = 24 * 60 * 60 * 1000;
var weekends = 0;
var current = new Date(startDate);

while (current <= endDate) {
    if (current.getDay() === 0 || current.getDay() === 6) {
        weekends++;
    }
    current.setDate(current.getDate() + 1);
}

var totalDays = Math.round((endDate - startDate) / msPerDay);
var workDays = totalDays - weekends;

WScript.StdOut.Write(`Work days: ${workDays}`);
```

## Best Practices

1. **Code Structure**
   - Use clear variable names
   - Add comments for complex logic
   - Break down complex operations
   - Follow JavaScript best practices

2. **Error Handling**
   - Implement try/catch blocks
   - Validate input data
   - Provide meaningful error messages
   - Handle edge cases

3. **Performance**
   - Optimize loops and data processing
   - Limit complexity of operations
   - Use appropriate data structures
   - Consider memory usage

4. **Output Formatting**
   - Use clear output structures
   - Include necessary delimiters
   - Format complex data appropriately
   - Consider downstream processing

## Common Patterns

### Input Validation Pattern
```javascript
function validateInput(value, type) {
    switch(type) {
        case 'number':
            return !isNaN(parseFloat(value)) && isFinite(value);
        case 'date':
            return !isNaN(new Date(value).getTime());
        case 'email':
            return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(value);
        default:
            return !!value && value.trim().length > 0;
    }
}

var input = '%UserInput%';
var type = '%ValidationType%';

if (!validateInput(input, type)) {
    WScript.StdOut.Write(`Invalid ${type} input`);
    return;
}
```

### Data Transformation Pattern
```javascript
var data = '%InputData%'.split(',');
var transformed = data
    .map(item => item.trim())
    .filter(Boolean)
    .map(item => ({
        original: item,
        modified: item.toUpperCase(),
        length: item.length
    }));

WScript.StdOut.Write(JSON.stringify(transformed, null, 2));
```

## Troubleshooting

1. **Common Issues**
   - Invalid variable references
   - Type conversion errors
   - Syntax errors in JavaScript
   - Timeout issues with long operations

2. **Debug Techniques**
   - Use structured error messages
   - Add intermediate output points
   - Check variable types explicitly
   - Log operation progress

3. **Performance Issues**
   - Monitor loop operations
   - Check data structure sizes
   - Validate timeout settings
   - Optimize complex calculations