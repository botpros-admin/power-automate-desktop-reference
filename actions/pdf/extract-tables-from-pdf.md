# Extract Tables from PDF

## Description
You can extract tables that are contained in a PDF file by using the Extract tables from PDF action. In the action properties you can define the PDF file and the range of pages that the tables will be extracted from. Under the advanced action properties you can define a password in case a the PDF file is protected, define if the table has headers or not, and finally if tables that cross page margins should be merged or not.

## Syntax
```
Pdf.ExtractTablesFromPDF.ExtractTables PDFFile: `[pdf file]` MultiPageTables: True SetFirstRowAsHeader: True ExtractedPDFTables=> ExtractedPDFTables
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| PDF file | Yes | File | - | The PDF file to extract tables from. Enter a file path, a variable containing a file or a text path |
| Page(s) to extract | Yes | All, Single, Range | All | Specifies how many pages to extract tables from: all pages, a single page or a range of pages |
| Single page number | Yes (if Single) | Numeric value | - | The number of the single page to extract tables from |
| From page number | Yes (if Range) | Numeric value | - | The first page number from the range of pages to extract tables from |
| To page number | Yes (if Range) | Numeric value | - | The last page number from the range of pages to extract tables from |
| Password | No | Direct encrypted input or Text value | - | The password of the PDF file. Leave this blank if the PDF isn't password protected |
| Merge tables that cross page margins | No | Boolean value | True | Specifies whether to merge tables that cross page margins in the specified page range |
| First line contains column names | No | Boolean value | True | Specifies whether the first line of table contains column names |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| ExtractedPDFTables | List of PDF table info | The extracted tables with their info as a list |

## Exceptions

| Exception | Description |
|-----------|-------------|
| PDF file doesn't exist | File doesn't exist on the given path |
| Invalid password | The given password is invalid |
| Failed to extract tables | Error while trying to extract tables |