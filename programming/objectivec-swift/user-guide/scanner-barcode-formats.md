---
layout: default-layout
title: Specify Barcode Formats for BarcodeScanner - Dynamsoft Barcode Reader for iOS
description: Learn how to configure barcode formats in the Dynamsoft Barcode Reader iOS SDK.
keywords: BarcodeScanner, scanner, iOS, barcode formats
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Specify Barcode Formats

There are two ways to configure barcode formats:

- Configure formats in code.
- Configure formats together with other settings in the template.

## Configure Formats in Your Code

Specify barcode formats using a combined value of `DSBarcodeFormat`.

- Use bitwise OR (`|`) to combine multiple formats.
- `DSBarcodeFormatDefault` includes all common formats (`DSBarcodeFormatOneD`, `DSBarcodeFormatGS1Databar`, `DSBarcodeFormatPDF417`, `DSBarcodeFormatQRCode`, `DSBarcodeFormatDataMatrix`, `DSBarcodeFormatAztec`, `DSBarcodeFormatMaxiCode`, `DSBarcodeFormatMicroQR`, `DSBarcodeFormatMicroPDF417`, and `DSBarcodeFormatGS1Composite`).
- Use `DSBarcodeFormatAll` to enable all supported formats.
- Use group values like `DSBarcodeFormatOneD` when appropriate.

### BarcodeScanner API

- `BarcodeScannerConfig.barcodeFormats`

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.barcodeFormats = DSBarcodeFormatOneD | DSBarcodeFormatQRCode;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.barcodeFormats = [.oneD, .qrCode]
```

**Related APIs**

- [`barcodeFormats`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#barcodeformats)

## Configure Formats in a Template

Barcode formats are specified in `BarcodeFormatIds` under `BarcodeReaderTaskSettingOptions`. For example:

```json
{
	"CaptureVisionTemplates": [
		{
			"ImageROIProcessingNameArray": [ "ROI_2D" ],
			"Name": "ReadCommon2D"
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
