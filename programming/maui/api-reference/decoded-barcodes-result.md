---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Barcode Reader Android Edition
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
class DecodedBarcodesResult
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Items`](#items) | *List<BarcodeResultItem>* | Get an array of `BarcodeResultItems`, which are the basic unit of the captured results. |
| [`RotationTransformMatrix`](#rotationtransformmatrix) | *Matrix* | Get the rotation transformation matrix of the original image relative to the rotated image. |
| [`OriginalImageHashId`](#originalimagehashid) | *string* | Get the hash id of the source image. You can use this ID to get the source image via [`IntermediateResultManager`]({{ site.dcv_maui_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html) class. |
| [`ErrorCode`](#errorcode) | *int* | Get the error code if an error occurs when processing the image. |
| [`ErrorMessage`](#errormessage) | *string* | Get the error message if an error occurs when processing the image. |

### Items

A list of [`BarcodeResultItem`](barcode-result-item.md), which is the basic unit of the captured results.

```csharp
List<BarcodeResultItem> Items { get; }
```

### RotationTransformMatrix

Get the rotation transformation matrix of the original image relative to the rotated image.

```csharp
Matrix RotationTransformMatrix { get; }
```

**Return Value**

The rotation transformation matrix

### OriginalImageHashId

Get the hash id of the source image. You can use this ID to get the source image via the [`IntermediateResultManager`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html) class.

```csharp
string OriginalImageHashId { get; }
```

**Return Value**

The hash id of the source image.

### ErrorCode

Get the error code of this result should something go wrong. A `DecodedBarcodesResult` will carry error information when the license module is missing or the process times out.

```csharp
int ErrorCode { get; }
```

### ErrorMessage

Get the error message of this result should something go wrong. A `DecodedBarcodesResult` will carry error information when the license module is missing or the process times out.

```csharp
string ErrorMessage { get; }
```
