---
layout: default-layout
title: EnumCapturedResultItemType - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumCapturedResultItemType of DBR Flutter Edition defines the accepted result types that the Capture Vision instance will output
keywords: captured result, flutter, capture vision, settings, barcode reader
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumCapturedResultItemType
---

# EnumCapturedResultItemType

`EnumCapturedResultItemType` is an enumeration that specifies the different types of results that a `CaptureVisionRouter` instance can output. Each functional product under the Capture Vision umbrella has its own unique result type(s). For instance, the Barcode Reader outputs the result type `barcode`, while the Document Normalizer outputs a `detectedQuad` or a `deskewedImage`.

> [!NOTE]
> Although most of the result types are unique to a certain functional product, the `originalImage` result type is shared between all of the functional products.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumCapturedResultItemType {
    originalImage,
    barcode,
    parsedResult
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `originalImage` | The original image on which the capture process was performed. This result type can be output by any of the Capture Vision functional products (Barcode Reader, Label Recognizer, and Document Normalizer). |
| `barcode` | The decoded barcode, which is the result at the end of a Barcode Reader task. |
| `parsedResult` | The parsed result, which is the result at the end of a Code Parser task. |
