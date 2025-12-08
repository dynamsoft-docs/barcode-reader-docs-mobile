---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Capture Vision React Native Edition
description: The DecodedBarcodesResult class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, DecodedBarcodesResult, api reference, barcode result, capture, flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodesResult
---

# DecodedBarcodesResult Class

The `DecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```tsx
interface DecodedBarcodesResult extends CapturedResultBase
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`items`](#items) | *List\<BarcodeResultItem\>?* | A list of [`BarcodeResultItem`](barcode-result-item.md), the basic unit representing a single barcode result. |

The following properties are inherited from [`CapturedResultBase`]({{ site.dcv_react_native_api }}core/captured-result-base.html):

| Properties | Types | Description |
| ---------- | ----- | ----------- |
| [`originalImageHashId`]({{ site.dcv_react_native_api }}core/captured-result-base.html#originalimagehashid) | *string* | The hash id of the original image. |
| [`rotationTransformMatrix`]({{ site.dcv_react_native_api }}core/captured-result-base.html#rotationtransformmatrix) | *Array<number>* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`]({{ site.dcv_react_native_api }}core/captured-result-base.html#errorcode) | *number* | The error code of this result. |
| [`errorMessage`]({{ site.dcv_react_native_api }}core/captured-result-base.html#errormessage) | *string* | The error message of this result. |

### items

An array of [`BarcodeResultItem`](barcode-result-item.md), the basic item representing a single barcode result and its associated info.

```tsx
items?: Array<BarcodeResultItem>;
```
