# Extract PDF File Pages to New PDF File

## Description
You can create a new PDF file by extracting pages from an existing PDF file by using the PDF file pages to a new PDF file action. In the action parameters you can define the PDF file to extract the pages from, the page(s) to be extracted, the location of the new PDF file and what should happen if a file with the same name and extension already exists.

## Syntax
```
Pdf.ExtractPages PDFFile: `[pdf file]` PageSelection: `[pages]` ExtractedPDFPath: `[output path]` IfFileExists: Pdf.IfFileExists.AddSequentialSuffix ExtractedPDFFile=> ExtractedPDF
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| PDF file | Yes | File | - | The PDF file to extract pages from. Enter a file path, a variable containing a file or a text path |
| Password | No | Direct encrypted input or Text value | - | The password of the PDF file. Leave this blank if the PDF isn't password protected |
| Page selection | Yes | Text value | - | The index numbers of the pages to keep (for example, 1,3,17-24) |
| Extracted PDF path | Yes | File | - | The path to store the extracted PDF file |
| If file exists | No | Overwrite, Don't overwrite, Add sequential suffix | Add sequential suffix | Specifies what to do in case the output PDF file already exists |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| ExtractedPDF | File | The new PDF file |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Invalid password | The given password is invalid |
| PDF file doesn't exist | File doesn't exist on the given path |
| Page out of bounds | Indicates that one or more pages are out of bounds of the PDF file |
| Invalid page selection | Indicates that the given pages aren't valid for the PDF file |
| Failed to extract new PDF | Indicates that an error occurred while trying to extract new PDF |