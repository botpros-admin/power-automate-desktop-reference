# Run VBScript

## Description
Executes custom VBScript code and retrieves its output into a variable. The action provides a specialized VB.Net environment configured for Power Automate Desktop (PAD).

## Syntax
```
Scripting.RunVBScript.RunVBScript VBScriptCode: $'''''' ScriptOutput=> VBScriptOutput
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| VBScriptCode | Yes | Text value | - | The VBScript code to execute |
| Fail after timeout | No | Boolean value | - | Whether the VBScript will run indefinitely or fail after a set period of time |
| Timeout | Yes (if Fail after timeout is true) | Numeric value | 10 | The maximum number of seconds to wait for the script to complete (-1 for indefinitely) |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| VBScriptOutput | Text value | The script's output |
| ScriptError | Text value | The errors that may occur during execution |

## Core Principles

1. **Native VB.Net Only**
   - Use only native VB.Net functions and methods
   - Avoid unnecessary imports
   - No external dependencies or libraries

2. **Input Validation**
   - Always check for null or empty values
   - Sanitize special characters
   - Use proper escaping for quotes and backslashes

3. **Output Formatting**
   - Wrap outputs in quotes for PAD compatibility
   - Format strings consistently
   - Handle line breaks properly

## Working Examples

### 1. Input Sanitization
```vbscript
inputText = If(String.IsNullOrEmpty(inputText), """", inputText.Replace("\", "\\").Replace("""", "\""").Replace("\r\n", "\n").Replace("\n", "\n").Replace("\t", "\t"))
inputText = """" & inputText & """"
```

### 2. HTML Cleanup
```vbscript
inputText = inputText.Replace("<br>", "\n").Replace("</p>", "\n").Replace("<p>", "").Replace("&nbsp;", " ").Replace("&amp;", "&")
inputText = inputText.Replace("&lt;", "<").Replace("&gt;", ">")
```

### 3. String Operations
```vbscript
' Convert to uppercase
inputText = inputText.ToUpper()

' Trim whitespace
inputText = inputText.Trim()

' Replace substring
inputText = inputText.Replace("oldValue", "newValue")
```

### 4. Numeric Operations
```vbscript
' Remove numeric characters
For Each c As Char In "0123456789"
    inputText = inputText.Replace(c.ToString(), "")
Next

' Keep only numeric characters
Dim result As String = ""
For Each c As Char In inputText
    If Char.IsDigit(c) Then
        result &= c
    End If
Next
inputText = result
```

### 5. Text Processing
```vbscript
' Remove multiple spaces
Do While inputText.Contains("  ")
    inputText = inputText.Replace("  ", " ")
Loop

' Split text into lines
resultArray = inputText.Split(New String() {Environment.NewLine}, StringSplitOptions.None)
```

### 6. Advanced String Manipulation
```vbscript
' Remove special characters
Dim result As String = ""
For Each c As Char In inputText
    If Char.IsLetterOrDigit(c) OrElse Char.IsWhiteSpace(c) Then
        result &= c
    End If
Next
inputText = result

' Reverse string
inputText = New String(inputText.Reverse().ToArray())
```

### 7. Array Operations
```vbscript
' Split string into array
resultArray = inputText.Split(","c)

' Join array into string
outputText = String.Join(",", inputArray)
```

## Best Practices

1. **Input Handling**
   - Validate all inputs before processing
   - Handle null or empty values gracefully
   - Sanitize special characters

2. **Code Structure**
   - Write code in a linear, step-by-step format
   - Keep operations simple and focused
   - Use meaningful variable names

3. **Error Prevention**
   - Include proper error handling
   - Validate inputs thoroughly
   - Handle edge cases appropriately

4. **Output Formatting**
   - Wrap strings in quotes
   - Format output consistently
   - Handle special characters properly

## Common Issues and Solutions

1. **Special Characters**
   - Always escape quotes and backslashes
   - Handle line breaks consistently
   - Consider encoding requirements

2. **Performance**
   - Keep operations simple
   - Avoid complex loops
   - Use efficient string operations

3. **Compatibility**
   - Use only native functions
   - Avoid external dependencies
   - Test with various input types