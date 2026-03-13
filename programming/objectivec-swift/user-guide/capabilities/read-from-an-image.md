---
layout: default-layout
title: Read from an Image - Dynamsoft Barcode Reader iOS
description: Learn how to read barcodes from an image using the Dynamsoft Barcode Reader iOS SDK.
keywords: user guide, read from an image, iOS, objective-c, swift
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# How to Read Barcodes from an Image

> [!Important]
> Features on this page are only available for the **Foundational APIs**.

> [!Note]
> Refer to the [DecodeFromAnImage sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeFromAnImage){:target="_blank"} for an example of decoding from the photo gallery.

The `capture` methods of the `CaptureVisionRouter` class are designed to process a single image.

```objc
- (DSCapturedResult *)captureFromFile:(NSString *)filePath templateName:(NSString *)templateName error:(NSError **)error;
- (DSCapturedResult *)captureFromFileBytes:(NSData *)fileBytes templateName:(NSString *)templateName error:(NSError **)error;
- (DSCapturedResult *)captureFromImage:(UIImage *)image templateName:(NSString *)templateName error:(NSError **)error;
- (DSCapturedResult *)captureFromBuffer:(NSData *)buffer width:(NSInteger)width height:(NSInteger)height stride:(NSInteger)stride format:(DSImagePixelFormat)format orientation:(NSInteger)orientation templateName:(NSString *)templateName error:(NSError **)error;
```

## Supported Image Types

The following image input types are supported:

1. An image specified by file path.
2. An image in memory (file bytes).
3. `UIImage`
4. [com.dynamsoft.core.basic_structures.ImageData]({{ site.dcvb_ios_api }}core/basic-structures/image-data.html)

> [!Note]
> When decoding with a file path, provide the full file path, including the extension. Supported extensions are ".bmp", ".jpg", ".png", ".gif", and single-page ".tiff".

## How to Specify Template Name

When using a `capture` method, `templateName` is required. You can specify either a preset template or a custom template name.

### Use a Preset Template

`EnumPresetTemplate.PT_READ_BARCODES_READ_RATE_FIRST` is recommended when processing an image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, strong) DSCaptureVisionRouter *cvr;
self.cvr = [[DSCaptureVisionRouter alloc] init];
DSCapturedResult *capturedResult = [self.cvr captureFromFile:@"" templateName:DSPresetTemplateReadBarcodes];
```
2. 
```swift
let capturedResult = try cvr.captureFromFile("Your-file-path", templateName: PresetTemplate.readBarcodes.rawValue)
```

### Use a Customized Template

For details, see [Parameters and Settings - Use a Customized Template](parameters-and-settings.md#use-a-customized-template).

## Code Snippet

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
do {
   let capturedResult = try cvr.captureFromFile("Your file path", templateName: PresetTemplate.readBarcodes.rawValue)
   if let decodedBarcodesResult = capturedResult.decodedBarcodesResult {
          for barcodeResultItem in decodedBarcodesResult.items {
             let barcodeText = barcodeResultItem.text
             let barcodeFormatString = barcodeResultItem.formatString
          }
   }
} catch {
}
```

- `CapturedResult`: The largest set of image processing results. `DecodedBarcodesResult` is one subset of `CapturedResult`.
- `DecodedBarcodesResult`: The set of barcode results. It contains an array of `BarcodeResultItem` objects and additional information.
- `BarcodeResultItem`: An object that represents a single decoded barcode.

Read [Understand Barcode Decoding Results](../understand-decoded-barcodes-results.md) for more information.
