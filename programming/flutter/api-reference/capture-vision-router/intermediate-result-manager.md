---
layout: default-layout
title: IntermediateResultManager Class - Dynamsoft Capture Vision Flutter
description: IntermediateResultManager class of DCV Flutter provides API to retrieve the intermediate results taken during the capture process.
keywords: intermediate, result, capture vision, original image, manager
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# IntermediateResultManager

The `IntermediateResultManager` class provides the API needed to manage the intermediate results that are produced during the capture process. Currently, the `IntermediateResultManager` is mainly used for when the user wants to retrieve the original image or frame that the captured result is taken from, especially in an interactive video scenario where the input is a camera feed.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class IntermediateResultManager
```

## Methods

### getOriginalImage

Retrieves the original image (as an ImageData object) associated with the captured result, based on the `originalImageHashId` of the [`CapturedResult`](captured-result.md).

```dart
Future<ImageData?> getOriginalImage(String hashId) async
```

**Remarks**

In order to get the hashID input parameter, please access the `originalImageHashId` of the [`CapturedResult`](captured-result.md). The `CapturedResult` can be a [`DecodedBarcodesResult`](decoded-barcodes-result.md) (if the Barcode Reader is used) and so the `originalImageHashId` can be obtained from the `DecodedBarcodesResult` object directly since it extends the `CapturedResult` class.

The method returns a [`ImageData`](image-data.md) object which contains all the info of the original image, including a byte array to represent the raw image.

## Code Snippet

```dart
..onDecodedBarcodesReceived = (DecodedBarcodesResult result) async {
    if (result.items?.isNotEmpty ?? false) {
    final intManager = CaptureVisionRouter.getIntermediateResultManager();
    final originalImage = await intManager.getOriginalImage(result.originalImageHashId);
    if (originalImage != null){
        print(originalImage.format); // verify that it is output in colour
        final filePath = "${directory.path}/dynamsoft_output.jpg"; // you can change this path to whatever works and that is accessible
        await ImageIO().saveToFile(originalImage, filePath, true); // saving the captured frame to the directory above
    }
    }
};
```