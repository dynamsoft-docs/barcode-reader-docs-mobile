---
layout: default-layout
title: ParsedResult Class - Dynamsoft Capture Vision Flutter Edition
description: The ParsedResult class represents the result of a code parsing process. It provides access to the individual parsed items resulting from a document or an encrypted text.
keywords: originalImageHashId, items, errorCode, ParsedResult, api reference, barcode result, capture, flutter, code parser
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ParsedResult
---

# ParsedResult Class

The `ParsedResult` class represents the result of a code parsing process. It provides access to the individual parsed items resulting from a document or an encrypted text.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class ParsedResult
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`items`](#items) | *List\<ParsedResultItem\>?* | A list of [`ParsedResultItem`](parsed-result-item.md), the basic unit representing a single parsed result from an encrypted text. |

The following properties are inherited from [`CapturedResult`](./capture-vision-router/captured-result.md):

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`originalImageHashId`](../capture-vision-router/captured-result.md#originalimagehashid) | *String* | The hash id of the original image. You can use this ID to get the original image via the `IntermediateResultManager` class. |
| [`rotationTransformMatrix`](../capture-vision-router/captured-result.md#rotationtransformmatrix) |  *Matrix4* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`](../capture-vision-router/captured-result.md#errorcode) | *int* | The error code associated with the capture result. |
| [`errorMessage`](../capture-vision-router/captured-result.md#errormessage) | *String* | The error message associated with the capture result. |

### items

A list of [`ParsedResultItem`](parsed-result-item.md), the basic unit representing a single parsed result from an encrypted text.

```dart
List<ParsedResultItem>? items;
```