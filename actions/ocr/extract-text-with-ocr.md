# Extract Text with OCR

## Description
Extract text from a given source using the given OCR engine.

## Syntax
```
OCR.ExtractTextWithOCR.ExtractTextFromScreenWithWindowsOcr WindowsOcrLanguage: OCR.WindowsOcrLanguage.English ImageWidthMultiplier: 1 ImageHeightMultiplier: 1 OcrText=> OcrText
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| OCR engine | Yes | Windows OCR engine, Tesseract engine, OCR engine variable | OCR engine variable | OCR engine to use |
| OCR engine variable | Yes | OCREngineObject | - | Engine for OCR operation |
| OCR source | Yes | Screen, Foreground window, Image on disk | Screen | Source for OCR |
| Image file path | Yes (if Image) | File | - | Path to image file |
| Search mode | Yes | Whole of specified source, Specific subregion only, Subregion relative to image | Whole of specified source | OCR area |
| Image | Yes (if subregion) | List of Images | - | Reference image |
| Tolerance | No | Numeric value | 10 | Image matching tolerance |
| X1, Y1 | Yes (if subregion) | Numeric value | - | Start coordinates |
| X2, Y2 | Yes (if subregion) | Numeric value | - | End coordinates |
| Windows OCR language | Yes | [List of languages] | English | Language for OCR |
| Use other language | No | Boolean value | False | Use custom Tesseract language |
| Language abbreviation | Yes (if custom) | Text value | - | Tesseract language code |
| Language data path | Yes (if custom) | Text value | - | Path to language data |
| Image width multiplier | No | Numeric value | 1 | Image width scaling |
| Image height multiplier | No | Numeric value | 1 | Image height scaling |
| Wait for image to appear | No | Boolean value | True | Wait for source image |
| Timeout | No | Numeric value | 5 | Operation timeout |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| OcrText | Text value | Extracted text result |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to extract text with OCR | OCR extraction failed |
| Image file not found | Source image missing |
| Landmark image not found | Reference image missing |
| Can't get text from screen in non-interactive mode | Not possible in non-interactive mode |
| Failed to create the OCR engine | Engine creation failed |
| Data path folder doesn't exist | Invalid data path |
| The selected Windows language pack isn't installed | Missing language pack |
| OCR engine not alive | Engine not responding |

## Notes
- OCR engine variable option is being deprecated
- For Tesseract custom languages, ensure proper language data files are installed
- Windows OCR requires corresponding language packs
- Use appropriate timeout values based on source complexity