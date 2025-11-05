---
layout: default-layout
title: CapturedResultReceiver Interface - Dynamsoft Capture Vision Flutter
description: CapturedResultReceiver interface of DCV Flutter edition is designed as a standardized way for retrieving captured results.
keywords: decoded barcodes, parsed results, captured results, CRR, result receiver, output, flutter, barcode reader
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# CapturedResultReceiver

The `CapturedResultReceiver` interface is designed as a standardized way for retrieving captured results in the Dynamsoft Capture Vision architecture. By implementing the `CapturedResultReceiver`, you will receive the callback of the various types of *captured results*, such a decoded barcode (Barcode Reader), a recognized text line (Label Recognizer), a detected quad (Document Normalizer), a normalized image (Document Normalizer), or parsed data (Code Parser). The `CapturedResultReceiver` can add a receiver for any type of captured result or for a specific type of captured result, based on the method that is implemented.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class CapturedResultReceiver
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`onCapturedResultReceived`](#oncapturedresultreceived) | This callback is triggered when any kind of captured result is available at the end of the recognition process. |
| [`onDecodedBarcodesReceived`](#ondecodedbarcodesreceived) | This callback is triggered when decoded barcode(s) are available at the end of the recognition process. |
| [`onParsedResultsReceived`](#onparsedreultsreceived) | This callback is triggered when decoded barcode(s) are available at the end of the recognition process. |

### onCapturedResultReceived

This callback method delivers a [`CapturedResult`](captured-result.md) - an object representing any kind of captured result item that is captured from an image or a video frame. The callback is triggered each time an image finishes processing, regardless of whether there is a valid result or not.

```dart
Future<void> Function(CapturedResult result)? onCapturedResultReceived;
```

**Parameters**

`result`: The captured result, an instance of [`CapturedResult`](captured-result.md).

### onDecodedBarcodesReceived

This callback method delivers a [`DecodedBarcodesResult`](decoded-barcodes-result.md), which is an object representing any captured result of type `CRIT_BARCODE` that is taken from an image or a video frame. The callback is triggered each time an image finishes processing, regardless of whether there is a valid result or not.

```dart
Future<void> Function(DecodedBarcodesResult result)? onDecodedBarcodesReceived;
```

**Parameters**

`result`: The decoded barcode result, an instance of [`DecodedBarcodesResult`](decoded-barcodes-result.md).

### onParsedReultsReceived

This callback method delivers a ParsedResult, which is an object representing any captured result of type `parsedResult` that is taken from an image or a video frame. The callback is triggered each time an image finishes processing, regardless of whether there is a valid result or not.

```dart
Future<void> Function(ParsedResult result)? onParsedResultsReceived;
```
