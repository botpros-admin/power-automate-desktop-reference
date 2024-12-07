# Extract Images from PDF

## Description
To extract images from a PDF file you can use the Extract images from PDF action. In the action parameters you can define the PDF file and the pages to extract images from, the naming convention of the extacted images and the target location of the saved images. You can also define a password if the PDF file is protected under the advanced settings.

## Syntax
```
Pdf.ExtractImagesFromPDF.ExtractImages PDFFile: `[pdf file]` ImagesName: `[image name]` ImagesFolder: `[folder path]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| PDF file | Yes | File | - | The PDF file to extract images from. Enter a file path, a variable containing a file or a text path |
| Password | No | Direct encrypted input or Text value | - | The password of the PDF file. Leave this blank if the PDF isn't password protected |
| Page(s) to extract | Yes | All, Single, Range | All | Specifies how many pages to extract: All pages, a single page or a range of pages |
| Single page number | Yes (if Single) | Numeric value | - | The number of the single page to extract images from |
| From page number | Yes (if Range) | Numeric value | - | The first page number from the range of pages to extract images from |
| To page number | Yes (if Range) | Numeric value | - | The last page number from the range of pages to extract images from |
| Image(s) name | Yes | Text value | - | How the name of the image(s) starts. Extracted image(s) name example: GivenName_1, GivenName_2 |
| Save image(s) to | Yes | Folder | - | The folder to save the extracted images as png files |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Invalid password | The given password is invalid |
| Failed to extract images | Indicates that an error occurred while extracting images from the given pages of the PDF |
| Folder doesn't exist | Indicates that the folder doesn't exist |
| PDF file doesn't exist | File doesn't exist on the given path |