# Power Automate Desktop Action Reference

This repository serves as a reference database for AI assistants to generate accurate, pastable Power Automate Desktop (PAD) action syntax. The content within each action file represents the exact, copyable text that appears when copying actions from within Power Automate Desktop.

## Purpose

1. To enable AI assistants to provide users with precise, copy-pastable Power Automate Desktop action syntax
2. To ensure generated subflows can be directly pasted into Power Automate Desktop without modification
3. To maintain a comprehensive library of exact PAD action formats as they appear when copied from the application

## Critical Syntax Rules for AI Assistants

### Do's
- Keep each action on a single line only - no line breaks or empty lines
- Use the exact action and parameter names as provided in the examples
- Maintain identical casing and spelling for all components
- Use backticks (``) as placeholders for values
- Place actual values by either:
  - Replacing the backticks entirely with the value, or
  - Placing the value between the backticks (test which works)
- Maintain exact spacing: one space after colons, one space between parameters
- Test any modifications in PAD before documenting

### Don'ts
- Do not use markdown or code blocks in the final snippet
- Do not add extra spaces or characters
- Do not alter parameter names or order
- Do not change enumerations without testing
- Do not include comments or explanations on the same line as the action
- Do not add quotes, parentheses, or brackets around values unless explicitly shown

## Action Categories

1. [Active Directory](./actions/active-directory/README.md)
2. [Clipboard](./actions/clipboard/README.md)
3. [Conditionals](./actions/conditionals/README.md)
4. [DateTime](./actions/datetime/README.md)
5. [File](./actions/file/README.md)
6. [Flow Control](./actions/flow-control/README.md)
7. [Folder](./actions/folder/README.md)
8. [HTTP](./actions/http/README.md)
9. [OCR](./actions/ocr/README.md)
10. [Outlook](./actions/outlook/README.md)
11. [Scripting](./actions/scripting/README.md)
12. [System](./actions/system/README.md)
13. [Variables](./actions/variables/README.md)

## Directory Structure

```
/actions/
  ├── [category]/
  │   ├── README.md         # Category overview and pastable syntax examples
  │   └── [action-name].md  # Individual action syntax and usage
  └── README.md            # Category index
```

## Documentation Format

Each action file contains:
- The exact, copy-pastable syntax as it appears when copied from PAD
- Required variables and their formats
- Example combinations with other actions
- Common usage patterns
- Any specific formatting requirements

## Usage Guidelines for AI Assistants

1. When a user requests a PAD flow or action:
   - Locate the appropriate action syntax in this repository
   - Combine actions as needed while maintaining exact syntax
   - Provide the complete, pastable result
   - Include any necessary variable declarations
   - Maintain proper action spacing and formatting

2. For multiple action combinations:
   - Preserve the exact syntax of each action
   - Ensure variable consistency across actions
   - Maintain proper flow structure and indentation
   - Include any required error handling

3. When providing flows:
   - Start with any necessary variable declarations
   - Include complete action syntax for each step
   - Maintain proper flow control structure
   - Ensure all variables are properly declared and used
   - Keep consistent formatting for direct pasting

## Example Usage

When a user requests "How to read a text file and write its contents to another file", provide the exact syntax:

```
PROCESS Read text from file
    File: '%MyFile%'
    Text: TextContent
    Encoding: TextEncoding.UTF8
END PROCESS

PROCESS Write text to file
    File: '%OutputFile%'
    Text: '%TextContent%'
    Encoding: TextEncoding.UTF8
    Write method: WriteTextToFile.Override
END PROCESS
```

Note: Test all snippets in PAD before providing them to users. The goal is to ensure every snippet can be pasted directly into PAD without any modification.