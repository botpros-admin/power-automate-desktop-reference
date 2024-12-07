# Wait for Text on Screen (OCR)

## Description
Wait until specific text appears/disappears on the screen, foreground window, or relative to an image using OCR.

## Syntax
```
WAIT (OCR.WaitForTextOnScreen.TextOnScreenToAppearWithWindowsOcr TextToFind: `[text]` IsRegex: False WindowsOcrLanguage: OCR.WindowsOcrLanguage.English SearchForTextOn: OCR.SearchTarget.EntireScreen ImageWidthMultiplier: 1 ImageHeightMultiplier: 1 TextLocationX=> LocationOfTextFoundX TextLocationY=> LocationOfTextFoundY)
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Wait for text to | Yes | Appear, Disappear | Appear | Wait condition |
| OCR engine type | Yes | Windows OCR engine, Tesseract engine, OCR engine variable | OCR engine variable | OCR engine to use |
| OCR engine variable | Yes | OCREngineObject | - | Engine for OCR operation |
| Text to find | Yes | Text value | - | Text to wait for |
| Is regular expression | No | Boolean value | False | Use regex pattern |
| Search for text on | Yes | Entire screen, Foreground window | Entire screen | Search scope |
| Search mode | Yes | Whole of specified source, Specific subregion only, Subregion relative to image | Whole of specified source | Search area |
| Image(s) | Yes (if using subregion) | List of Images | - | Reference images for subregion |
| Tolerance | No | Numeric value | 10 | Image matching tolerance |
| X1, Y1 | Yes (if subregion) | Numeric value | - | Start coordinates |
| X2, Y2 | Yes (if subregion) | Numeric value | - | End coordinates |
| Windows OCR language | Yes | [List of languages] | English | Language for OCR |
| Fail with timeout error | No | Boolean value | False | Enable timeout |
| Image width multiplier | No | Numeric value | 1 | Image width scaling |
| Image height multiplier | No | Numeric value | 1 | Image height scaling |
| Image matching algorithm | No | Basic, Advanced | Basic | Image search algorithm |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| LocationOfTextFoundX | Numeric value | X coordinate where text found |
| LocationOfTextFoundY | Numeric value | Y coordinate where text found |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Can't check if text exists in non-interactive mode | Not possible in non-interactive mode |
| Invalid subregion coordinates | Invalid coordinates |
| Failed to analyze text with OCR | OCR analysis failed |
| Failed to create the OCR engine | Engine creation failed |
| Data path folder doesn't exist | Invalid data path |
| The selected Windows language pack isn't installed | Missing language pack |
| OCR engine not alive | Engine not responding |
| Timeout error | Action timed out |

## Notes
- Regex uses .NET engine format
- OCR engine variable option is being deprecated
- For language packs besides English, ensure required Windows language pack is installed