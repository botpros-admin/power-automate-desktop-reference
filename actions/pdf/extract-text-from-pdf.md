# Extract Text from PDF

## Description
You can extract text from a PDF file by using the "Extract text from PDF" action. In the action properties you can define the source PDF file and the pages that text should be extracted from. Under the advanced action properties you can define a password in case the PDF file is protected and if the engine should optimize for structured data or not.

## Syntax
```
Pdf.ExtractTextFromPDF.ExtractText PDFFile: `[pdf file]` DetectLayout: False ExtractedText=> ExtractedPDFText
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| PDF file | Yes | File | - | The PDF file to extract text from. Enter a file path, a variable containing a file or a text path |
| Page(s) to extract | Yes | All, Single, Range | All | Specifies how many pages to extract: All pages, a single page or a range of pages |
| Single page number | Yes (if Single) | Numeric value | - | The number of the single page to extract text from |
| From page number | Yes (if Range) | Numeric value | - | The first page number from the range of pages to extract text from |
| To page number | Yes (if Range) | Numeric value | - | The last page number from the range of pages to extract text from |
| Password | No | Direct encrypted input or Text value | - | The password of the PDF file. Leave this blank if the PDF isn't password protected |
| Optimize for structured data | No | Boolean value | False | Specify whether to detect formatted layout in the document and extract text accordingly |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| ExtractedPDFText | Text value | The extracted text |

## Exceptions

| Exception | Description |
|-----------|-------------|
| PDF file doesn't exist | File doesn't exist on the given path |
| Invalid password | The given password is invalid |
| Failed to extract text | Error while trying to extract text |