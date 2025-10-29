---
layout: default-layout
title: CaptureVisionRouter - Dynamsoft Capture Vision Flutter
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

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class CaptureVisionRouter
```

## Capture Methods

| Method | Description |
| --- | --- |
| [`capture`](#capture) | Processes an image using the specified template and outputs a CapturedResult. |
| [`captureFile`](#capturefile) | Processes an image from a file path using the specified template. |
| [`captureFileBytes`](#capturefilebytes) | Processes an image from a byte array using the specified template. |
| [`startCapturing`](#startcapturing) | Starts the capturing process using the specified template. |
| [`stopCapturing`](#stopcapturing) | Stops the capturing process and closes the camera. |

## Settings Management Methods

| Method | Description |
| --- | --- |
| [`getSimplifiedSettings`](#getsimplifiedsettings) | Returns a subset of the full applied settings as a SimplifiedCaptureVisionSettings object. |
| [`getTemplateNames`](#gettemplatenames) | Returns a list of all available Capture Vision template names. |
| [`initSettings`](#initsettings) | Initializes the settings using a JSON template string. |
| [`initSettingsFromFile`](#initsettingsfromfile) | Initializes the settings using a JSON template file. |
| [`outputSettings`](#outputsettings) | Outputs the specified template's settings as a JSON string. |
| [`outputSettingsToFile`](#outputsettingstofile) | Outputs the specified template's settings to a JSON file. |
| [`resetSettings`](#resetsettings) | Resets all settings to their default values. |
| [`switchCapturingTemplate`](#switchcapturingtemplate) | Switches the template used by the Capture Vision Router instance to the specified template name. |
| [`updateSettings`](#updatesettings) | Updates the specified template settings using a SimplifiedCaptureVisionSettings object. |

## Resource Management Methods

| Method | Description |
| --- | --- |
| [`clearDLModelBuffers`](#cleardlmodelbuffers) | Clears the buffer used by deep learning models to free up memory and resources. |
| [`getIntermediateResultManager`](#getintermediateresultmanager) | Retrieves the IntermediateResultManager instance which allows the user to snap the original image. |
| [`setGlobalIntraOpNumThreads`](#setglobalintraopnumthreads) | Sets the global number of threads used internally by the library for model execution. |

## Result Management Methods

| Method | Description |
| --- | --- |
| [`addResultFilter`](#addresultfilter) | Adds a result filter to process the captured results. |
| [`addResultReceiver`](#addresultreceiver) | Adds a result receiver that listens for any captured results. |
| [`removeAllResultFilters`](#removeallresultfilters) | Removes all the result filters from the Capture Vision Router instance. |
| [`removeAllResultReceivers`](#removeallresultreceivers) | Removes all result receivers from the Capture Vision Router instance. |
| [`removeResultFilter`](#removeresultfilter) | Removes a previously added result filter. |
| [`removeResultReceiver`](#removeresultreceiver) | Removes a previously added result receiver. |

## Input Source Methods

| Method | Description |
| --- | --- |
| [`setInput`](#setinput) | Sets up an image source to provide images for continuous processing. |

### addResultFilter

Adds a result filter to process the captured results. This filter is of type MultiFrameResultCrossFilter.

```dart
Future<void> addResultFilter(MultiFrameResultCrossFilter filter)
```

**Remarks**

Adding a result filter is not needed for the operation of the Capture Vision Router, but it can help improve the accuracy of the results by verifying them across multiple image frames.

### addResultReceiver

Adds a result receiver that listens for any captured results. This receiver is a callback function that is triggered once a captured result is produced - whether it is successful, cancelled, or failed.

```dart
Future<void> addResultReceiver(CapturedResultReceiver receiver)
```

**Remarks**

To learn about the different result receivers that you can add, please refer to [`CapturedResultReceiver`](captured-result-receiver.md). Please note that adding a result receiver is necessary to getting the results that are produced by the Capture Vision Router instance.

### capture

Processes an image using the specified template and processes it - outputting a [`CapturedResult`](captured-result.md) containing the result(s) if there was no exception or error thrown.

```dart
Future<CapturedResult> capture(ImageData imageData, String templateName) async
```

**Remarks**

The template that is used during processing can be a preset template (one of [`EnumPresetTemplate`](../enum/preset-template.md)) or a customized JSON template that you create or that is provided to you by the Dynamsoft team. This method is to be used specifically when working with *static images*.

### captureFile

Processes an image from a file (specified by a file path) using the specified template, returning the [`CapturedResult`](captured-result.md) once the process is done.

```dart
Future<CapturedResult> captureFile(String filePath, String templateName) async
```

**Remarks**

The template that is used during processing can be a preset template (one of [`EnumPresetTemplate`](../enum/preset-template.md)) or a customized JSON template that you create or that is provided to you by the Dynamsoft team. This method is to be used specifically when working with *static images*.

### captureFileBytes

Processes an image from a byte array using the specified template, returning the [`CapturedResult`](captured-result.md) once the process is done.

```dart
Future<CapturedResult> captureFileBytes(Uint8List bytes, String templateName) async
```

**Remarks**

The template that is used during processing can be a preset template (one of [`EnumPresetTemplate`](../enum/preset-template.md)) or a customized JSON template that you create or that is provided to you by the Dynamsoft team. This method is to be used specifically when working with *static images*.

### clearDLModelBuffers

Clears the buffer used by deep learning models to free up memory and resources used by the Capture Vision Router instance for its operation.

```dart
static Future<void> clearDLModelBuffers()
```

### getIntermediateResultManager

Retrieves the [`IntermediateResultManager`](intermediate-result-manager.md) instance which allows the user to snap the original image that contains the captured result.

```dart
IntermediateResultManager getIntermediateResultManager()
```

**Remarks**

In order to get the original image that the captured result was taken from (especially in an interactive video scenario where the input is a camera feed), you will need to use the [`getOriginalImage`](intermediate-result-manager.md#getoriginalimage) method of the `IntermediateResultManager` instance.

### getSimplifiedSettings

Returns a subset of the full applied settings as a [`SimplifiedCaptureVisionSettings`](simplified-capture-vision-settings.md) object. This object contains the simplified settings of the Capture Vision Router instance, which in turn contains the simplified settings of the functional product used.

```dart
Future<SimplifiedCaptureVisionSettings?> getSimplifiedSettings(String templateName) async
```

**Remarks**

The templateName parameter represents the Capture Vision template that has been applied, whether it is a [preset template](../enum/preset-template.md) or a custom template defined in a JSON template file or string. To learn how to use the `getSimplifiedSettings`, please refer to this [section of the Foundational User Guide](../../foundational-user-guide.md#using-simplifiedcapturevisionsettings).

### getTemplateNames

Returns a list of all available Capture Vision template names when a custom template is used via `initSettings`.

```dart
Future<List<String>> getTemplateNames() async
```

**Remarks**

A single template file/string can contain multiple Capture Vision templates, so this method will list each of the template(s) contained within the single template file/string. Each template can then be used with any of the capture methods, but only one at a time.

### initSettings

Initializes the settings of the `CaptureVisionRouter` instance using a JSON template (as a JSON string). To learn how to use a customized JSON template, please refer to this [section of the Foundational User Guide](../../foundational-user-guide.md#using-a-json-template).

```dart
Future<void> initSettings(String content)
```

### initSettingsFromFile

Initializes the settings of the `CaptureVisionRouter` instance using a JSON template (as a JSON file). To learn how to use a customized JSON template, please refer to this [section of the Foundational User Guide](../../foundational-user-guide.md#using-a-json-template).

```dart
Future<void> initSettingsFromFile(String filePath) async
```

### outputSettings

Outputs the specified Capture Vision template's settings as a JSON string. If `includeDefaultValues` is set to true, the output will include the default settings values.

```dart
Future<String?> outputSettings(String templateName, bool includeDefaultValues) async
```

### outputSettingsToFile

Outputs the specified Capture Vision template's settings to a JSON file. If `includeDefaultValues` is set to true, the output will include the default settings values.

```dart
Future<void> outputSettingsToFile(String templateName, String filePath, bool includeDefaultValues) async
```

### removeAllResultFilters

Removes all the result filters from the Capture Vision Router instance.

```dart
Future<void> removeAllResultFilters()
```

### removeAllResultReceivers

Removes all result receivers from the Capture Vision Router instance.

```dart
Future<void> removeAllResultReceivers()
```

### removeResultFilter

Removes a previously added result filter.

```dart
Future<void> removeResultFilter(MultiFrameResultCrossFilter filter)
```

### removeResultReceiver

Removes a previously added result receiver.

```dart
Future<void> removeResultReceiver(CapturedResultReceiver receiver)
```

### resetSettings

Resets all of the settings to their default values.

```dart
Future<void> resetSettings() async
```

### setGlobalIntraOpNumThreads

Sets the global number of threads used internally by the library for model execution. This parameter could help regulate the resources needed to operate the Capture Vision Router instance.

```dart
static Future<void> setGlobalIntraOpNumThreads(int intraOpNumThreads)
```

**Remarks**

Setting the `intraOpNumThreads` input parameter to 0 lets the system decide the optimal number of threads. The default value is 0.

### setInput

Sets up an image source to provide images for continuous processing. This method is mainly used when configuring a camera (via the [`CameraEnhancer`](camera-enhancer.md)) as an input source.

```dart
Future<void> setInput(ImageSourceAdapter input) async
```

**Remarks**

In most cases, the `ImageSourceAdapter` that will be used is a Camera Enhancer instance to allow the user to use their phone's built-in camera. <!-- If there is a case where an external camera or image source is being used, please refer to Image -->

### startCapturing

Starts the capturing process using the specified template. Any result(s) (of type [`CapturedResult`](captured-result.md)) that are received while the capture process is underway will be relayed by a result receiver, which is a callback function that is triggered once a captured result is found.

```dart
Future<void> startCapturing(String templateName)
```

**Remarks**

The template that is used during processing can be a preset template (one of [`EnumPresetTemplate`](../enum/preset-template.md)) or a customized JSON template that you create or that is provided to you by the Dynamsoft team.

### stopCapturing

Stops the capturing process and closes the camera.

```dart
Future<void> stopCapturing()
```

### switchCapturingTemplate

Switched the template used by the Capture Vision Router instance to the specified template name.

```dart
Future<void> switchCapturingTemplate(String templateName) async
```

**Remarks**

For the `templateName` input parameter, this can be either the name of the `CaptureVisionTemplate` in a custom JSON template file/string or the name of one of the preset templates available via [`EnumPresetTemplate`](../enum/preset-template.md).

### updateSettings

Updates the specified template settings of the `CaptureVisionRouter` instance using a [`SimplifiedCaptureVisionSettings`](simplified-capture-vision-settings.md) object. To learn how to update the settings using the SimplifiedCaptureVisionSettings class - please refer to this [section of the Foundational User Guide](../../foundational-user-guide.md#using-simplifiedcapturevisionsettings).

```dart
Future<void> updateSettings(String templateName, SimplifiedCaptureVisionSettings settings)
```

**Remarks**

For the `templateName` input parameter, this can be either the name of the `CaptureVisionTemplate` in a custom JSON template file/string or the name of one of the preset templates available via [`EnumPresetTemplate`](../enum/preset-template.md).

