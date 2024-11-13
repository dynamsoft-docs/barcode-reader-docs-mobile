---
layout: default-layout
title: SimplifiedCaptureVisionSettings Class - Dynamsoft Capture Vision Router Lite MAUI
description: SimplifiedCaptureVisionSettings class of DCV MAUI edition provides settings for capturing and recognizing images with the CaptureVisionRouter class.
keywords: roi, result item type, min interval, timeout
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# SimplifiedCaptureVisionSettings

The `SimplifiedCaptureVisionSettings` class contains settings for capturing and recognizing images with the `CaptureVisionRouter` class.

## Definition

*Namespace:* Dynamsoft.CaptureVisionRouter.Maui

*Assembly:* Dynamsoft.CaptureVisionRouterLite.Maui

```csharp
class SimplifiedCaptureVisionSettings
```

## Properties

| Property | Type | Description |
| ---------- | ---- | ----------- |
| [`CapturedResultItemTypes`](#capturedresultitemtypes) | *EnumCapturedResultItemType* | Specifies the type(s) of CapturedItem(s) that will be captured. |
| [`Roi`](#roi) | *[Quadrilateral]({{ site.dcv_maui_api }}core/quadrilateral.html)* | Specifies the region of interest (ROI) where the image capture and recognition will take place. |
| [`RoiMeasuredInPercentage`](#roimeasuredinpercentage) | *bool* | Specifies whether the ROI is measured in pixels or as a percentage of the image size. |
| [`MaxParallelTasks`](#maxparalleltasks) | *int* | Specifies the maximum number of parallel tasks that can be used for image capture and recognition. |
| [`MinImageCaptureInterval`](#minimagecaptureinterval) | *int* | Set the minimum capture interval. It is measured in millisecond. |
| [`Timeout`](#timeout) | *int* | Specifies the maximum time (in milliseconds) allowed for image capture and recognition. |
| [`BarcodeSettings`](#barcodesettings) | *[SimplifiedBarcodeReaderSettings]({{ site.dbr_maui_api }}simplified-barcode-reader-settings.html)* | Specifies the settings for `DynamsoftBarcodeReader` tasks. |

### CapturedResultItemTypes

Specifies the type(s) of CapturedItem(s) that will be captured.

```csharp
EnumCapturedResultItemType CapturedResultItemTypes { get; set; }
```

### Roi

Specifies the region of interest (ROI) where the image capture and recognition will take place.

```csharp
Quadrilateral Roi { get; set; }
```

### RoiMeasuredInPercentage

Specifies whether the ROI is measured in pixels or as a percentage of the image size.

```csharp
bool RoiMeasuredInPercentage { get; set; }
```

### MaxParallelTasks

Specifies the maximum number of parallel tasks that can be used for image capture and recognition.

```csharp
int MaxParallelTasks { get; set; }
```

### MinImageCaptureInterval

Set the minimum capture interval. It is measured in millisecond.

```csharp
int MinImageCaptureInterval { get; set; }
```

### Timeout

Specifies the maximum time (in milliseconds) allowed for image capture and recognition.

```csharp
int Timeout { get; set; }
```

### BarcodeSettings

Specifies the settings for `DynamsoftBarcodeReader` tasks with a [`SimplifiedBarcodeReaderSettings`]({{ site.dbr_maui_api }}simplified-barcode-reader-settings.html) object.

```csharp
SimplifiedBarcodeReaderSettings BarcodeSettings { get; set; }
```
