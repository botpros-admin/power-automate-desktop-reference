# Run .NET Script

## Description
Executes .NET (C#/VB.NET) script code and retrieves its output.

## Syntax
```
Scripting.RunDotNetScript Language: System.DotNetActionLanguageType.CSharp
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Language | Yes | C#/VB.NET | C# | The language of the script |
| .NET script imports | No | Text value | - | The .NET script imports to include |
| References to be loaded | No | Folder | - | Root path where .NET DLL references are located |
| Script parameters | No | Script Parameters | - | Values of parameters defined in the script |
| .NET code to run | Yes | Text value | - | The .NET code to run |

## Output Variables

Output variables depend on the configuration made using the Script Parameters window.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to run the .NET script | Indicates a problem running the provided .NET script |

## Example Usage

```csharp
# Basic C# script
Scripting.RunDotNetScript Language: System.DotNetActionLanguageType.CSharp
using System;

class Program {
    static void Main() {
        Console.WriteLine("Hello from C#");
    }
}

# Data processing
Scripting.RunDotNetScript Language: System.DotNetActionLanguageType.CSharp
using System;
using System.Linq;

class Program {
    static void Main() {
        var numbers = new[] { 1, 2, 3, 4, 5 };
        var sum = numbers.Sum();
        Console.WriteLine($"Sum: {sum}");
    }
}
```

## Best Practices
1. Include necessary using statements
2. Handle script parameters properly
3. Set output parameters to non-null values
4. Reference required assemblies
5. Format output for easy parsing