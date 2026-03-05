---
layout: default-layout
title: Read from an Image - Dynamsoft Barcode Reader Android
description: Learn how to read barcodes from an image using the Dynamsoft Barcode Reader Android SDK.
keywords: user guide, read from an image, Android, java, kotlin
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# How to Read Barcodes from an Image

> [!Important]
> Features on this page are only available for the **Foundational APIs**.

> [!Note]
> Refer to the [DecodeFromAnImage sample](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/DecodeFromAnImage){:target="_blank"} for an example of decoding from the photo gallery.

The `capture` methods of the `CaptureVisionRouter` class are designed to process a single image.

```java
CapturedResult capture(String filePath, String templateName) {}
CapturedResult capture(byte[] fileBytes, String templateName) {}
CapturedResult capture(Bitmap bitmap, String templateName) {}
CapturedResult capture(ImageData imageData, String templateName) {}
```

## Supported Image Types

The following image input types are supported:

1. An image specified by file path.
2. An image in memory (file bytes).
3. `android.graphics.Bitmap`
4. [com.dynamsoft.core.basic_structures.ImageData]({{ site.dcvb_android_api }}core/basic-structures/image-data.html)

> [!Note]
> When decoding with a file path, provide the full file path, including the extension. Supported extensions are ".bmp", ".jpg", ".png", ".gif", and single-page ".tiff".

## How to Specify Template Name

When using a `capture` method, `templateName` is required. You can specify either a preset template or a custom template name.

### Use a Preset Template

`EnumPresetTemplate.PT_READ_BARCODES_READ_RATE_FIRST` is recommended when processing an image.

```java
CapturedResult capturedResult = mRouter.capture("Your-file-path",EnumPresetTemplate.PT_READ_BARCODES_READ_RATE_FIRST);
```

### Use a Customized Template

For details, see [Parameters and Settings - Use a Customized Template](parameters-and-settings.md#use-a-customized-template).

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

- `CapturedResult`: The largest set of image processing results. `DecodedBarcodesResult` is one subset of `CapturedResult`.
- `DecodedBarcodesResult`: The set of barcode results. It contains an array of `BarcodeResultItem` objects and additional information.
- `BarcodeResultItem`: An object that represents a single decoded barcode.

Read [Understand Barcode Decoding Results](../understand-decoded-barcodes-results.md) for more information.
