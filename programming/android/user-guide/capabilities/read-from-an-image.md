---
layout: default-layout
title: Read from an Image - Dynamsoft Barcode Reader for Android User Guide
description: This page explores how to read barcodes from an image with Dynamsoft Barcode Reader Android SDK.
keywords: user guide, read from an image, Android, java, kotlin
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# How to Read Barcodes from an Image

> [!Note]
> Reference the [DecodeFromAnImage sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/DecodeFromAnImage){:target="_blank"} for how to decode from the album.

The `capture` methods of `CaptureVisionRouter` class are designed to process a single image.

```java
CapturedResult capture(String filePath, String templateName) {}
CapturedResult capture(byte[] fileBytes, String templateName) {}
CapturedResult capture(Bitmap bitmap, String templateName) {}
CapturedResult capture(ImageData imageData, String templateName) {}
```

## Supported Image Types

The following image types are supported:

1. Image with the file path.
2. Image in memory (file bytes).
3. `android.graphics.Bitmap`
4. [com.dynamsoft.core.basic_structures.ImageData]({{ site.dcvb_android_api }}core/basic-structures/image-data.html)

> [!Note]
> When decoding with a file path, you should input the full file path with the extension name. Supported extensions: ".bmp", ".jpg", ".png", ".gif" or one-page ".tiff".

## How to Specify Template Name

When using the capture method, a `templateName` is required. You can specify either a preset template or the name a custom template.

### Use a Preset Template

`EnumPresetTemplate.PT_READ_BARCODES_READ_RATE_FIRST` is suggested for the template name when processing an image.

```java
CapturedResult capturedResult = mRouter.capture("Your-file-path",EnumPresetTemplate.PT_READ_BARCODES_READ_RATE_FIRST);
```

### Use Customized Template

View [Parameters and Settings - Use a Customized Template](parameters-and-settings.md#use-a-customized-template) for details.

## Code Snippet

```java
CapturedResult capturedResult = mRouter.capture("Your file path",EnumPresetTemplate.PT_READ_BARCODES_READ_RATE_FIRST);
DecodedBarcodesResult decodedBarcodesResult = capturedResult.getDecodedBarcodesResult();
BarcodeResultItem[] barcodeResultItems = decodedBarcodesResult.getItems();
for(BarcodeResultItem barcodeResultItem: barcodeResultItems)
{
    String barcodeText = barcodeResultItem.getText();
    String barcodeFormatString = barcodeResultItem.getFormatString();
}
```

- `CapturedResult`: The biggest set of image processing results. `DecodedBarcodesResult` is one of the subsets of the `CapturedResult`.
- `DecodedBarcodesResult`: The set of barcode-type results. It contains an array of `BarcodeResultItem` and additional information.
- `BarcodeResultItem`: Object that represents a single decoded barcode.

Read [Understand Barcode Decoding Results](../understand-decoded-barcodes-results.md) for more information.
