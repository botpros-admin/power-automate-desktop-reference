# Run JavaScript

## Description
Executes custom JavaScript code and retrieves its output into a variable.

## Syntax
```
Scripting.RunJavascript.RunJavascript JavascriptCode: $'''''' ScriptOutput=> JavascriptOutput
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| JavaScriptCode | Yes | Text value | - | The JavaScript code to execute |
| Fail after timeout | No | Boolean value | - | Whether the JavaScript script will run indefinitely or fail after a set period of time |
| Timeout | Yes (if Fail after timeout is true) | Numeric value | 10 | The maximum number of seconds to wait for the script to complete (-1 for indefinitely) |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| JavascriptOutput | Text value | The script's output |
| ScriptError | Text value | The errors that may occur during execution |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to run script in the allotted time | Indicates a problem running the provided script in the allotted time |

## Example Usage

```javascript
# Calculate array sum
Scripting.RunJavascript.RunJavascript JavascriptCode: $'''const nums = [1, 2, 3, 4, 5];
const sum = nums.reduce((a, b) => a + b, 0);
console.log(`Sum: ${sum}`);''' ScriptOutput=> ArraySum

# Manipulate JSON data
Scripting.RunJavascript.RunJavascript JavascriptCode: $'''
const data = {
  name: "John",
  age: 30,
  city: "New York"
};
console.log(JSON.stringify(data, null, 2));
''' ScriptOutput=> JsonData
```

## Best Practices
1. Use proper error handling with try/catch
2. Avoid infinite loops
3. Use console.log for output
4. Set appropriate timeouts
5. Format output for easy parsing