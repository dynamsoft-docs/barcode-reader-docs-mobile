---
layout: default-layout
title: Advanced Features (Foundational Edition) - Dynamsoft Barcode Reader Flutter Edition
description: The advanced features guide for the foundational edition of Dynamsoft Barcode Reader Flutter gives the user insight on how to utilize some of the more complicated features of the Capture Vision library.
keywords: advanced, customization, foundational, Flutter, barcode reader
needAutoGenerateSidebar: true
noTitleIndex: true
---

# Advanced Features Guide (Foundational Edition)

The Capture Vision (and in turn, its functional products like the Barcode Reader) comes with a number of advanced features that can prove to be useful in certain scenarios or provides the user with more info related to the core results. In this guide, we will explore some of these advanced features and how to implement them using the Capture Vision Foundational API.

## Retrieving the Original Image

One of the main advanced features that the library offers is the ability to retrieve the original image or frame that contains the captured result when it is recognized from a video stream via a camera. For example, if you are scanning barcodes, the library will always give you back the barcode result of course, but you can also configure it so that it sends back an image of the barcode as well - whether it is stored in a database or used for further analysis.

The main class that helps you achieve this is the [`IntermediateResultManager`](../api-reference/capture-vision-router/intermediate-result-manager.md), and through that class you can retrieve the original image using the `getOriginalImage` method.

Here is an implementation of the `onDecodedBarcodesReceived` callback that will get the original image as well as the actual barcode result.

```dart
..onDecodedBarcodesReceived = (DecodedBarcodesResult result) async {
      if (result.items?.isNotEmpty ?? false) {
        final intManager = CaptureVisionRouter.getIntermediateResultManager();
        final originalImage = await intManager.getOriginalImage(result.originalImageHashId);
        if (originalImage != null){
          print(originalImage.format); // verify that it is output in colour
          final filePath = "${directory.path}/dynamsoft_output.jpg"; // you can change this path to whatever works and that is accessible
          ImageManager().saveToFile(originalImage, filePath, true); // saving the captured frame to the directory above
        }
        await _cvr.stopCapturing();
        var displayString = result.items?.map((item) => "Format: ${item.formatString}\nText: ${item.text}").join('\n\n');
        
        showTextDialog("Barcodes Count: ${result.items?.length ?? 0}", displayString ?? "", () {
          _cvr.startCapturing(_templateName);
        });
      }
    };
```

## Enabling Haptic Feedback

Another feature that the Capture Vision library offers is the ability to trigger a couple of haptic feedback reactions once a barcode is found. This is done via the [`FeedBack`](api-reference/capture-vision-router/feedback.md) class - and it should be called in the result callback function so that the haptic feedback occurs once a barcode is successfully decoded.

> [!NOTE]
> To see how the FeedBack class should be implemented to trigger these haptic feedback reactions once a barcode is found, please visit the [`FeedBack` API](../api-reference/capture-vision-router/feedback.md) page.

## Increasing Result Consistency using the MultiFrameResultCrossFilter

The [`MultiFrameResultCrossFilter`](../api-reference/capture-vision-router/multi-frame-cross-filter.md) class allows the user to increase the accuracy of the results that the library outputs. By comparing the same result over multiple frames, the `MultiFrameResultCrossFilter` is able to verify that the result is accurate. The number of frames that get compared is configurable, but by default it would be five frames if the result cross verification is enabled.

`MultiFrameResultCrossFilter` also helps eliminate the issue of duplicated barcodes, eliminating any dupliated barcode scans to count against the scan quota of your license (kf you are on a per-scan license).

Please see the code snippet below on how to activate the different filters of the `MultiFrameResultCrossFilter`.

```dart
final MultiFrameResultCrossFilter _multiFilter = MultiFrameResultCrossFilter();
_multiFilter.enableResultCrossVerification(EnumCapturedResultItemType.barcode.value, true);
_multiFilter.enableResultDeduplication(EnumCapturedResultItemType.barcode.value, true);
_multiFilter.enableLatestOverlapping(EnumCapturedResultItemType.barcode.value, true);
_multiFilter.setMaxOverlappingFrames(EnumCapturedResultItemType.barcode.value, 5);
_multiFilter.setDuplicateForgetTime(EnumCapturedResultItemType.barcode.value, 5000);
_cvr.addResultFilter(_multiFilter);
```