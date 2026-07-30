---
layout: default-layout
title: Configure Barcode Formats - Dynamsoft Barcode Reader iOS
description: Learn how to configure barcode formats in the Dynamsoft Barcode Reader iOS SDK.
keywords: barcode formats, iOS, objective-c, swift
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Configure Barcode Formats

There are two ways to configure barcode formats:

- Configure formats in code.
- Configure formats together with other settings in the template.

## Configure Formats in Your Code

Specify barcode formats using a combined value of [`EnumBarcodeFormat`]({{ site.dbr_ios_api }}enum/barcode-format.html).

- Use bitwise OR (`|`) to combine multiple formats.
- `EnumBarcodeFormat.BF_DEFAULT` includes all common formats (`BF_ONED`, `BF_GS1_DATABAR`, `BF_PDF417`, `BF_QR_CODE`, `BF_DATAMATRIX`, `BF_AZTEC`, `BF_MAXICODE`, `BF_MICRO_QR`, `BF_MICRO_PDF417`, and `BF_GS1_COMPOSITE`).
- Use `EnumBarcodeFormat.BF_ALL` to enable all supported formats.
- Use group values like `EnumBarcodeFormat.BF_ONED` when appropriate.

### Use Foundational API

- `SimplifiedCaptureVisionSettings.barcodeSettings.barcodeFormatIds`

Example:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, strong) DSCaptureVisionRouter *cvr;
self.cvr = [[DSCaptureVisionRouter alloc] init];
NSError *error = nil;
DSSimplifiedCaptureVisionSettings *settings = [self.cvr getSimplifiedSettings:DSPresetTemplateReadBarcodes error:&error];
DSSimplifiedBarcodeReaderSettings *barcodeSettings = settings.barcodeSettings;
barcodeSettings.barcodeFormatIds = DSBarcodeFormatQRCode | DSBarcodeFormatDataMatrix;
[self.cvr updateSettings:DSPresetTemplateReadBarcodes settings:settings error:&error];
```
2. 
```swift
guard let settings = try? cvr.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue) else {
   return
}
settings.barcodeSettings?.barcodeFormatIds = [.dataMatrix, .qrCode]
do {
   try cvr.updateSettings(PresetTemplate.readBarcodes.rawValue, settings:settings)
} catch {
   print("update runtimeSettings error:\(error.localizedDescription)")
}
```

### Use BarcodeScanner API

- `BarcodeScannerConfig.setBarcodeFormats(long format)`

Example:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
// QR Code + DataMatrix
config.barcodeFormats = DSBarcodeFormatQRCode | DSBarcodeFormatDataMatrix;
```
2. 
```swift
let config = BarcodeScannerConfig()
// QR Code + DataMatrix
config.barcodeFormats = [.qrCode, .dataMatrix]
```

> [!Note]
> If you are already using a customized template, you usually do not need to specify formats again in code. See [Use a Customized Template](parameters-and-templates.md#use-a-customized-template) for details.

## Configure Formats in a Template

Barcode formats are specified in `BarcodeFormatIds` under `BarcodeReaderTaskSettingOptions`. For example:

```json
{
  "CaptureVisionTemplates": [
    {
      "ImageROIProcessingNameArray": [ "ROI_2D" ],
      "Name": "ReadCommon2D",
    }
  ],
  "TargetROIDefOptions": [
    {
      "Name": "ROI_2D",
      "TaskSettingNameArray": [ "Task_2D" ]
    }
  ],
  "BarcodeReaderTaskSettingOptions": [
    {
      "Name": "Task_2D",
      "BarcodeFormatIds": [ "BF_QR_CODE", "BF_DATAMATRIX", "BF_PDF417", "BF_MAXICODE" ],
      "SectionArray": [
        {
          "Section": "ST_BARCODE_LOCALIZATION",
          "ImageParameterName": "ip"
        },
        {
          "Section": "ST_BARCODE_DECODING",
          "ImageParameterName": "ip"
        }
      ]
    }
  ],
  "ImageParameterOptions": [
    {
      "Name": "ip"
    }
  ]
}
```

For common formats, you can download and use the preset templates below:

| Barcode Format(s) | Template |
| ----------------- | -------- |
| EAN13, EAN8, UPC_A, UPC_E, GS1 Databar | [ReadOneDRetail.json](https://github.com/Dynamsoft/barcode-reader-mobile-samples/blob/main/ios/BarcodeScannerAPISamples/ScenarioOrientedSamples/src/main/assets/Templates/ReadOneDRetail.json) |
| Code128, Code39, ITF, Codabar, MSI Code | [ReadOneDIndustrial.json](https://github.com/Dynamsoft/barcode-reader-mobile-samples/blob/main/ios/BarcodeScannerAPISamples/ScenarioOrientedSamples/src/main/assets/Templates/ReadOneDIndustrial.json) |
| QR Code | [ReadQR.json](https://github.com/Dynamsoft/barcode-reader-mobile-samples/blob/main/ios/BarcodeScannerAPISamples/ScenarioOrientedSamples/src/main/assets/Templates/ReadQR.json) |
| Data Matrix | [ReadDataMatrix.json](https://github.com/Dynamsoft/barcode-reader-mobile-samples/blob/main/ios/BarcodeScannerAPISamples/ScenarioOrientedSamples/src/main/assets/Templates/ReadDataMatrix.json) |
| PDF417 | [ReadPDF417.json](https://github.com/Dynamsoft/barcode-reader-mobile-samples/blob/main/ios/BarcodeScannerAPISamples/ScenarioOrientedSamples/src/main/assets/Templates/ReadPDF417.json) |
| Aztec | [ReadAztec.json](https://github.com/Dynamsoft/barcode-reader-mobile-samples/blob/main/ios/BarcodeScannerAPISamples/ScenarioOrientedSamples/src/main/assets/Templates/ReadAztec.json) |
| QR Code, Data Matrix, PDF417 | [ReadCommon2D.json](https://github.com/Dynamsoft/barcode-reader-mobile-samples/blob/main/ios/BarcodeScannerAPISamples/ScenarioOrientedSamples/src/main/assets/Templates/ReadCommon2D.json) |
| DotCode | [ReadDotCode.json](https://github.com/Dynamsoft/barcode-reader-mobile-samples/blob/main/ios/BarcodeScannerAPISamples/ScenarioOrientedSamples/src/main/assets/Templates/ReadDotCode.json) |
