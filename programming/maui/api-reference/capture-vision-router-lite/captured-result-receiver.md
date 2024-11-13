---
layout: default-layout
title: CapturedResultReceiver Interface - Dynamsoft Capture Vision Router Lite MAUI
description: CapturedResultReceiver interface of DCV MAUI edition is designed as a standardized way for retrieving captured results.
keywords: decoded barcodes, parsed results, captured results, CRR, result receiver, output
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# CapturedResultReceiver

The `CapturedResultReceiver` interface is designed as a standardized way for retrieving captured results in the Dynamsoft Capture Vision architecture. By implementing the `CapturedResultReceiver`, you will receive the callback of the various types of captured results, such as original image, decoded barcode, recognized text line, detected quad, normalized image, or parsed data. The `CapturedResultReceiver` can add a receiver for any type of captured result or for a specific type of captured result, based on the method that is implemented.

## Definition

*Namespace:* Dynamsoft.CaptureVisionRouter.Maui

*Assembly:* Dynamsoft.CaptureVisionRouterLite.Maui

```csharp
interface ICapturedResultReceiver
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`OnCapturedResultReceived`](#oncapturedresultreceived) | This callback method delivers a `CapturedResult`, which is an object containning all kinds of captured result items that are captured from the image. |
| [`OnDecodedBarcodesReceived`](#ondecodedbarcodesreceived) | This callback method delivers a `DecodedBarcodesResult`, which is an object containning all `CRIT_BARCODE` typed captured result items that are captured from the image. |

### OnCapturedResultReceived

This callback method delivers a `CapturedResult`, which is an object containning all kinds of captured result items that are captured from the image. The callback is triggered each time when an image finishes its processing.

```csharp
void OnCapturedResultReceived(CapturedResult result);
```

**Parameters**

`[in] result`: The captured result, an instance of [`CapturedResult`](captured-result.md).

### OnDecodedBarcodesReceived

This callback method delivers a `DecodedBarcodesResult`, which is an object containning all `CRIT_BARCODE` typed captured result items that are captured from the image. The callback is triggered each time when an image finishes its processing.

```csharp
void OnDecodedBarcodesReceived(DecodedBarcodesResult result);
```

**Parameters**

`[in] result`: The decoded barcode result, an instance of `DecodedBarcodesResult`.
