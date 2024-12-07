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
| OCR engine | Yes | Windows OCR engine, Tesseract engine, OCR engine variable | OCR engine variable | The OCR engine to use |
| OCR engine variable | Yes | OCREngineObject | - | Engine for OCR operation |
| OCR source | Yes | Screen, Foreground window, Image on disk | Screen | Source for OCR |
| Image file path | Yes (if Image) | File | - | Path to image file |
| Search mode | Yes | Whole of specified source, Specific subregion only, Subregion relative to image | Whole of specified source | OCR area |
| Windows OCR language | Yes | [List of languages] | English | Language for OCR |
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
- Ensure required language packs are installed
- Use appropriate timeout values for source type