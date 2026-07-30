---
layout: default-layout
title: Receive Results - Dynamsoft Barcode Reader iOS
description: Learn how to receive captured results when using Dynamsoft Barcode Reader iOS edition.
keywords: Receive Results, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Receive Results

## Receive Results from DSCapturedResultReceiver

If you only need barcode results, use `onDecodedBarcodesReceived`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface ViewController () <DSCapturedResultReceiver>
- (void)setUpDCV {
    [self.cvr addResultReceiver:self];
}
- (void)onDecodedBarcodesReceived:(DSDecodedBarcodesResult *)result {
    // Add your code to use the DSDecodedBarcodesResult
}
```
2. 
```swift
class ViewController: UIViewController, CapturedResultReceiver {
    func setUpDCV() {
        cvr.addResultReceiver(self)
    }
    func onDecodedBarcodesReceived(_ result: DecodedBarcodesResult) {
        // Add your code to use the DecodedBarcodesResult
    }
}
```

If you need multiple result types at the same time, `onCapturedResultReceived` is more convenient.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)onCapturedResultReceived:(DSCapturedResult *)result {
    if (result.items.count > 0) {
        for (DSCapturedResultItem *item in result.items) {
            // Use the captured result items you need here.
        }
    }
}
```
2. 
```swift
func onCapturedResultReceived(_ result: CapturedResult) {
    if let items = result.items, items.count > 0 {
        for item in items {
            // Use the captured result items you need here.
        }
    }
}
```

## Receive Results from Capture Methods

The result is returned as a `CapturedResult` object when using `capture` methods. You can get the types you want from the `CapturedResult` object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError *error = nil;
DSCapturedResult *capturedResult = [self.cvr captureFromFile:@"Your file path" templateName:DSPresetTemplateReadBarcodes error:&error];
DSDecodedBarcodesResult *decodedBarcodesResult = capturedResult.decodedBarcodesResult;
for (DSBarcodeResultItem *barcodeResultItem in decodedBarcodesResult.items) {
   NSString *barcodeText = barcodeResultItem.text;
   NSString *barcodeFormatString = barcodeResultItem.formatString;
}
```
2. 
```swift
let capturedResult = try cvr.captureFromFile("Your file path", templateName: PresetTemplate.readBarcodes.rawValue)
if let decodedBarcodesResult = capturedResult.decodedBarcodesResult,
   let barcodeResultItems = decodedBarcodesResult.items {
    for barcodeResultItem in barcodeResultItems {
        let barcodeText = barcodeResultItem.text
        let barcodeFormatString = barcodeResultItem.formatString
    }
}
```

## Receive Results from DSIntermediateResultReceiver

To use `DSIntermediateResultReceiver`, get the `DSIntermediateResultManager` from `DSCaptureVisionRouter` first. Then add a result receiver to the intermediate result manager for the intermediate result types you want to observe.

Intermediate results are useful when you need to inspect earlier algorithm stages, debug processing, or build custom workflows based on localized or transformed barcode data.

**Related APIs**

- [`getIntermediateResultManager`]({{ site.dcvb_ios_api }}capture-vision-router/intermediate-result.html#getintermediateresultmanager)
- [`DSIntermediateResultManager`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html)
- [`DSIntermediateResultReceiver`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/intermediate-result-receiver.html)