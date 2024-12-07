# Merge PDF Files

## Description
Merges multiple PDF files into a new one. You can use the Merge PDF files action to take two or more PDF files and merge them into a single file. The files to be merged can be provided either in the form of a list, or enclosed in double quotes and separated by a delimiter. You can also provide passwords for the PDF files, in case they are password-protected.

## Syntax
```
Pdf.MergeFiles PDFFiles: `[pdf files]` MergedPDFPath: `[output path]` IfFileExists: Pdf.IfFileExists.AddSequentialSuffix PasswordDelimiter: $''',''' MergedPDF=> MergedPDF
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| PDF files | Yes | List of Files | - | The files to merge. Enclose multiple files in double quotes (") and separate them by a delimiter, or use a list of files |
| Merged PDF path | Yes | File | - | The path to store the merged PDF |
| If file exists | No | Overwrite, Don't overwrite, Add sequential suffix | Add sequential suffix | Specifies what to do in case the destination file already exists |
| Passwords | No | Direct encrypted input or Text value | - | The delimited passwords. The order should be the same as the order of the input PDFs. Leave this blank if the PDFs aren't password protected |
| Delimiter | No | Text value | , | A custom password delimiter. This delimiter shouldn't be part of any of the passwords |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| MergedPDF | File | The merged PDF file |

## Exceptions

| Exception | Description |
|-----------|-------------|
| PDF file doesn't exist | File doesn't exist on the given path |
| Invalid password | The given password is invalid |
| Failed to merge PDF files | Indicates that an error occurred while merging the files |