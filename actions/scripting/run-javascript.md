# Run JavaScript

## Description
Executes custom JavaScript code and retrieves its output into a variable. This action provides a specialized JavaScript environment configured specifically for Power Automate Desktop (PAD), with unique syntax for variable handling and output.

## Syntax
```
Scripting.RunJavascript.RunJavascript JavascriptCode: $'''''' ScriptOutput=> JavascriptOutput
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
| JavascriptOutput | Text value | The script's output. Captures output from WScript.StdOut.Write or WScript.Echo |
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

### Output Methods
```javascript
// Primary output method
WScript.StdOut.Write('Output data');

// Alternative output method
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
WScript.StdOut.Write(num.toString());
```

## Comprehensive Examples

### 1. Variable Manipulation
```javascript
// Basic variable manipulation
var greeting = '%Greeting%';
WScript.StdOut.Write(greeting);

// Character replacement
var match = '%Match%';
match = match.replace(/-/g, "").replace(/O/g, "0");
WScript.StdOut.Write(match);

// String concatenation and case modification
var firstName = '%FirstName%';
var lastName = '%LastName%';
var fullName = (firstName + " " + lastName).toUpperCase();
WScript.StdOut.Write(fullName);
```

### 2. Numeric Operations
```javascript
// Parse and calculate
var num1 = parseFloat('%Number1%');
var num2 = parseFloat('%Number2%');
WScript.StdOut.Write(num1 + num2);

// Generate random number
var randomNum = Math.floor(Math.random() * 100) + 1;
WScript.StdOut.Write(randomNum);
```

### 3. Conditional Logic
```javascript
// Status check
var status = '%Status%';
if (status === "Active") {
    WScript.StdOut.Write("The user is active.");
} else {
    WScript.StdOut.Write("The user is inactive.");
}

// Substring check
var text = '%Text%';
if (text.includes("Success")) {
    WScript.StdOut.Write("The operation was successful.");
} else {
    WScript.StdOut.Write("Operation failed.");
}
```

### 4. Array Operations
```javascript
// Process comma-separated values
var items = '%CommaSeparatedValues%'.split(',');
for (var i = 0; i < items.length; i++) {
    WScript.StdOut.Write(items[i] + "\n");
}

// Array calculation
var nums = [1, 2, 3, 4, 5];
var sum = nums.reduce((a, b) => a + b, 0);
WScript.StdOut.Write(`Sum: ${sum}`);
```

### 5. Error Handling
```javascript
// Basic error handling
try {
    var value = '%SomeValue%';
    var result = parseInt(value) * 10;
    WScript.StdOut.Write(result);
} catch (e) {
    WScript.StdOut.Write("Error: " + e.message);
}

// Validation with error handling
try {
    var input = '%Input%';
    if (!input || input.trim() === '') {
        throw new Error('Input is empty');
    }
    WScript.StdOut.Write(input.toUpperCase());
} catch (e) {
    WScript.StdOut.Write("Validation Error: " + e.message);
}
```

### 6. Date Operations
```javascript
// Calculate date difference
var startDate = new Date('%StartDate%');
var endDate = new Date('%EndDate%');
var difference = (endDate - startDate) / (1000 * 60 * 60 * 24);
WScript.StdOut.Write(difference);

// Format date
var date = new Date('%CurrentDate%');
WScript.StdOut.Write(
    date.getFullYear() + '-' +
    String(date.getMonth() + 1).padStart(2, '0') + '-' +
    String(date.getDate()).padStart(2, '0')
);
```

### 7. JSON Processing
```javascript
// Parse and access JSON
var jsonString = '%JsonString%';
try {
    var jsonObject = JSON.parse(jsonString);
    WScript.StdOut.Write(jsonObject.name);
} catch (e) {
    WScript.StdOut.Write("JSON Error: " + e.message);
}

// Create and format JSON
var data = {
    name: "%Name%",
    age: parseInt('%Age%'),
    city: "%City%"
};
WScript.StdOut.Write(JSON.stringify(data, null, 2));
```

### 8. String Manipulation
```javascript
// Extract substring
var input = '%Input%';
var extracted = input.substring(0, 5);
WScript.StdOut.Write(extracted);

// String reversal with validation
var str = '%String%';
if (str && str.length > 0) {
    var reversedStr = str.split('').reverse().join('');
    WScript.StdOut.Write(reversedStr);
} else {
    WScript.StdOut.Write("Empty string provided");
}
```

## Error Handling Guidelines

### 1. Basic Error Structure
```javascript
try {
    // Your code here
    var result = someOperation();
    WScript.StdOut.Write(result);
} catch (e) {
    WScript.StdOut.Write("Error: " + e.message);
}
```

### 2. Input Validation
```javascript
if (!('%Variable%')) {
    WScript.StdOut.Write("Error: Required variable is missing");
    return;
}
```

### 3. Type Checking
```javascript
var num = '%Number%';
if (isNaN(parseFloat(num))) {
    WScript.StdOut.Write("Error: Invalid number format");
    return;
}
```

## Best Practices

1. **Variable Handling**
   - Always use %VariableName% syntax for PAD variables
   - Convert types explicitly (strings to numbers, etc.)
   - Validate variable existence before use

2. **Output Management**
   - Use WScript.StdOut.Write for consistent output
   - Format complex data structures clearly
   - Include error messages in output when appropriate

3. **Error Prevention**
   - Implement proper error handling with try/catch
   - Validate all inputs before processing
   - Use appropriate type conversion

4. **Code Structure**
   - Avoid infinite loops
   - Set appropriate timeouts for long operations
   - Format output for easy parsing
   - Comment complex logic

5. **Performance**
   - Optimize loops and data processing
   - Handle large datasets efficiently
   - Consider memory usage in long scripts

## Common Issues and Solutions

1. **Variable Not Found**
   - Verify variable name spelling
   - Check for proper %Variable% syntax
   - Ensure variable exists in PAD flow

2. **Type Conversion Errors**
   - Always validate before conversion
   - Use appropriate parsing methods
   - Handle null/undefined cases

3. **Timeout Issues**
   - Optimize long-running operations
   - Set appropriate timeout values
   - Consider breaking up large operations

4. **Output Formatting**
   - Use consistent output structure
   - Format complex data appropriately
   - Handle special characters properly