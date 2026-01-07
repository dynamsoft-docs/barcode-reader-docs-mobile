---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Barcode Reader MAUI Edition
description: The DecodedBarcodesResult class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, DecodedBarcodesResult, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodesResult
---

# DecodedBarcodesResult Class

The `DecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
class DecodedBarcodesResult : CapturedResultBase
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Items`](#items) | *BarcodeResultItem[]* | Get an array of `BarcodeResultItems`, which are the basic unit of the captured results. |

The following properties are inherited from [`CapturedResultBase`]({{ site.dcv_maui_api }}core/captured-result-base.html):

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`OriginalImageHashId`]({{ site.dcv_maui_api }}core/captured-result-base.html#originalimagehashid) | *string* | Represents the hash id of the original image. |
| [`RotationTransformMatrix`]({{ site.dcv_maui_api }}core/captured-result-base.html#rotationtransformmatrix) | *Matrix* | Represents the rotation transformation matrix of the original image relative to the rotated image. |
| [`ErrorCode`]({{ site.dcv_maui_api }}core/captured-result-base.html#errorcode) | *int* | Represents the error code of this result. |
| [`ErrorMessage`]({{ site.dcv_maui_api }}core/captured-result-base.html#errormessage) | *string* | Represents the error message of this result. |

### Items

A list of [`BarcodeResultItem`](barcode-result-item.md), which is the basic unit of the captured results.

```csharp
BarcodeResultItem[]? Items { get; }
```
