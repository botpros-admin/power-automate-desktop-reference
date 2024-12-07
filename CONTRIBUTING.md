# Contributing to Power Automate Desktop Reference

## ATTENTION AI AGENTS - READ THIS FIRST

This document contains **mandatory instructions** for contributing to the Power Automate Desktop Reference documentation. You MUST follow these guidelines exactly.

## Critical Requirements

### 1. Documentation Structure
Every action documentation MUST contain these exact sections in this order:
```markdown
# [Action Name]

## Description
[Clear description of what the action does]

## Syntax
```
[Exact.Copy.Syntax Parameter: `` Output=> Variable]
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
[Fill with actual parameters]

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
[Fill with actual outputs]

## Exceptions

| Exception | Description |
|-----------|-------------|
[Fill with actual exceptions]

## Example Usage

```
[Actual working example code]
```

## Best Practices
1. [Practice 1]
2. [Practice 2]
```

### 2. Content Requirements

**MANDATORY ELEMENTS:**
- Parameter tables MUST include ALL parameters
- Syntax examples MUST be exact and copyable
- Examples MUST be tested and working
- All possible exceptions MUST be documented

### 3. File Organization

**REQUIRED STRUCTURE:**
1. Place files in correct category folder
2. Use kebab-case for filenames (e.g., `get-file-contents.md`)
3. Include README.md in each folder
4. Maintain consistent formatting

### 4. Formatting Rules

**MUST FOLLOW:**
- Use pipe tables for parameters and variables
- Use code blocks with appropriate language tags
- Use standardized spacing
- Maintain consistent header levels

### 5. Examples and Best Practices

**REQUIREMENTS:**
- Include at least one working example
- Show common use cases
- Document error handling
- Provide performance considerations

### 6. Validation Steps

**BEFORE SUBMISSION:**
1. Verify all sections are present
2. Check syntax examples are correct
3. Test all example code
4. Validate parameter tables
5. Confirm exception documentation

## Pull Request Process

**REQUIRED STEPS:**
1. Create feature branch from main
2. Follow exact documentation format
3. Test all example code
4. Update relevant indexes
5. Submit PR with clear description

## Quality Checklist

**VERIFY THESE ITEMS:**
- [ ] All required sections present
- [ ] Syntax is exact and tested
- [ ] Parameters fully documented
- [ ] Examples are working
- [ ] Exceptions documented
- [ ] Best practices included

## Example Template

```markdown
# Get File Contents

## Description
Retrieves the contents of a specified file.

## Syntax
```
File.GetContents Path: `[file path]` Contents=> FileContents
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Path | Yes | Text | - | Full path to file |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| FileContents | Text | The contents of the file |

## Exceptions

| Exception | Description |
|-----------|-------------|
| FileNotFound | File does not exist |
| AccessDenied | Permission error |

## Example Usage

```
File.GetContents Path: `C:\temp\file.txt` Contents=> FileContents
```

## Best Practices
1. Always check file existence
2. Handle exceptions
3. Use proper path formatting
```

## REMEMBER
- Follow format exactly
- Include all sections
- Test all examples
- Document thoroughly
- Maintain consistency