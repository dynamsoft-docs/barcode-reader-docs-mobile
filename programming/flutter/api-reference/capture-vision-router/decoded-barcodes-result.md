---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Capture Vision Flutter Edition
description: The DecodedBarcodesResult class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, DecodedBarcodesResult, api reference, barcode result, capture, flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodesResult
---

# DecodedBarcodesResult Class

The `DecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class DecodedBarcodesResult
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`items`](#items) | *List\<BarcodeResultItem\>?* | A list of [`BarcodeResultItem`](barcode-result-item.md), the basic unit representing a single barcode result. |

The following properties are inherited from [`CapturedResult`](./capture-vision-router/captured-result.md):

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`originalImageHashId`](../capture-vision-router/captured-result.md#originalimagehashid) | *String* | The hash id of the original image. You can use this ID to get the original image via the `IntermediateResultManager` class. |
| [`rotationTransformMatrix`](../capture-vision-router/captured-result.md#rotationtransformmatrix) |  *Matrix4* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`](../capture-vision-router/captured-result.md#errorcode) | *int* | The error code associated with the capture result. |
| [`errorMessage`](../capture-vision-router/captured-result.md#errormessage) | *String* | The error message associated with the capture result. |

### items

A list of [`BarcodeResultItem`](barcode-result-item.md), the basic unit representing a single barcode result and its associated info.

```dart
List<BarcodeResultItem>? items;
```
