---
layout: default-layout
title: CaptureVisionRouter - Dynamsoft Capture Vision Router Lite Flutter
description: CaptureVisionRouter class of Dynamsoft Capture Vision Router contains all of the core methods to use Dynamsoft Capture Vision.
keywords: CaptureVisionRouter, Barcode Reader, capture, flutter, foundational
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: CaptureVisionRouter
---

# CaptureVisionRouter Class

The `CaptureVisionRouter` class defines how a user interacts with image-processing and semantic-processing Dynamsoft products in their applications.

A `CaptureVisionRouter` instance accepts and processes images from an image source and returns processing results which may contain final results or intermediate results. The instance can also process video frames coming from a camera or a different image source as well, therefore providing the ability to capture results via an interactive video scenario or from static images.

<!-- This class follows the singleton pattern. Use instance to get the shared instance. -->

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class CaptureVisionRouter
```

## Methods

### capture

Captures an image using the specified template and processes it - outputting a [`CapturedResult`](captured-result.md) containing the result(s) if there was no exception or error thrown. This method is to be used specifically when working with *static images*.

```dart
Future<CapturedResult> capture( ImageData imageData, String templateName )
```

#### Remarks

The template that is used during processing can be a preset template (one of [`EnumPresetTemplate`](../enum/preset-template.md)) or a customized JSON template that you create or that is provided to you by the Dynamsoft team.

### startCapturing

Starts the capturing process using the specified template. Any result(s) (of type [`CapturedResult`](captured-result.md)) that are received while the capture process is underway will be relayed by a result receiver, which is a callback function that is triggered once a captured result is found.

```dart
Future<void> startCapturing( String templateName )
```

#### Remarks

The template that is used during processing can be a preset template (one of [`EnumPresetTemplate`](../enum/preset-template.md)) or a customized JSON template that you create or that is provided to you by the Dynamsoft team.

### stopCapturing

Stops the capturing process and closes the camera.

```dart
Future<void> stopCapturing()
```

### initSettings

Initializes the settings of the `CaptureVisionRouter` instance using a JSON template (as a JSON string). To learn how to use a customized JSON template, please refer to this [section of the Foundational User Guide](../../foundational-user-guide.md#using-a-json-template).

```dart
Future<void> initSettings( String content )
```

### updateSettings

Updates the specified template settings of the `CaptureVisionRouter` instance using a [`SimplifiedCaptureVisionSettings`](simplified-capture-vision-settings.md) object. To learn how to update the settings using the SimplifiedCaptureVisionSettings class - please refer to this [section of the Foundational User Guide](../../foundational-user-guide.md#using-simplifiedcapturevisionsettings).

```dart
Future<void> updateSettings( String templateName, SimplifiedCaptureVisionSettings settings )
```

**Remarks**

For the `templateName` input parameter, this can be either the name of the `CaptureVisionTemplate` in a custom JSON template file/string or the name of one of the preset templates available via [`EnumPresetTemplate`](../enum/preset-template.md).

