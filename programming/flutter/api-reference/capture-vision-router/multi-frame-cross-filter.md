---
layout: default-layout
title: MultiFrameResultCrossFilter Class - Dynamsoft Capture Vision Flutter
description: MultiFrameResultCrossFilter class of DCV Flutter provides a filter for managing and filtering results.
keywords: filter, capture vision, barcode reader, flutter, multiframeresultcrossfilter, result
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# MultiFrameResultCrossFilter

The `MultiFrameResultCrossFilter` class provides a filter that allows the library to manage and filter results by crosschecking the results across multiple images frames. This filter will compare consecutive frames of the video stream to perform operations like cross-verification, deduplication, and overlapping result management.

> [!NOTE]
>  This filter is especially handy in increasing the accuracy when trying to capture barcodes, documents, or MRZ zones via a camera in an interactive video scenario.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class MultiFrameResultCrossFilter
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`destroy`](#destroy) | Destroys the `MultiFrameResultCrossFilter` instance and releases the related resources on the native side. |
| [`enableLatestOverlapping`](#enablelatestoverlapping) | Enables or disables the latest overlap result filtering. |
| [`enableResultCrossVerification`](#enableresultcrossverification) | Enables or disables result cross verification for the specified result item types. |
| [`enableResultDeduplication`](#enableresultdeduplication) | Enables or disables result deduplication for the specified result item types. |
| [`getDuplicateForgetTime`](#getduplicateforgettime) | Returns the amount of time that the deduplication filter takes effect for the specified result item type(s). |
| [`getMaxOverlappingFrames`](#getmaxoverlappingframes) | Returns the maximum number of overlapping frames to check for the specified result item type(s). |
| [`isLatestOverlappingEnabled`](#islatestoverlappingenabled) | Checks if the latest overlapping filter is on for the specified result item type(s). |
| [`isResultCrossVerificationEnabled`](#isresultcrossverificationenabled) | Checks if the cross verification filter is on for the specified result item type(s). |
| [`isResultDeduplicationEnabled`](#isresultdeduplicationenabled) | Checks if the deduplication filter is on for the specified result item type(s). |
| [`setDuplicateForgetTime`](#setduplicateforgettime) | Defines the amount of time that the deduplication filter takes effect for the specified result item type(s). |
| [`setMaxOverlappingFrames`](#setmaxoverlappingframes) | Sets the maximum number of overlapping frames to check when the latest overlap filter is on. |

### destroy

Destroys the `MultiFrameResultCrossFilter` instance and releases the related resources on the native side.

```dart
Future<void> destroy()
```

### enableLatestOverlapping

Enables or disables the latest overlap result filtering. Latest overlap filtering helps in managing results that overlap in the most recent frames.

```dart
Future<void> enableLatestOverlapping(int resultItemTypes, bool enable)
```

**Remarks**

`resultItemTypes` is a bitmask representing the result item types to apply the filter to - this value can be a combined value of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md). `enable` determines whether to enable or disable the filter process.

### enableResultCrossVerification

Enables or disables result cross verification for the specified result item types (represented as a combination of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md)). Cross verification helps in validating results across multiple frames, improving accuracy as a result.

```dart
Future<void> enableResultCrossVerification(int resultItemTypes, bool enable)
```

**Remarks**

`resultItemTypes` is a bitmask representing the result item types to apply the filter to - this value can be a combined value of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md). `enable` determines whether to enable or disable the filter process.

### enableResultDeduplication

Enables or disables result deduplication for the specified result item types (represented as a combination of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md)). If this filter is activated, the library will not scan a barcode for an amount of time again after it is scanned successfully for the first time. In order to set the amount of time that the barcode is remembered, please refer to `setDuplicateForgetTime`.

```dart
Future<void> enableResultDeduplication(int resultItemTypes, bool enable)
```

**Remarks**

`resultItemTypes` is a bitmask representing the result item types to apply the filter to - this value can be a combined value of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md). `enable` determines whether to enable or disable the filter process.

### getDuplicateForgetTime

Returns the amount of time, in *milliseconds*, that the deduplication filter takes effect for the specified result item type(s).

```dart
Future<int> getDuplicateForgetTime(int type)
```

**Remarks**

`type` is a bitmask representing the result item types to apply the filter to - this value can be a combined value of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md).

### getMaxOverlappingFrames

Returns the maximum number of overlapping frames to check for the specified result item type(s) when the latest overlap filter is on.

```dart
Future<int> getMaxOverlappingFrames(int type)
```

**Remarks**

`type` is a bitmask representing the result item types to apply the filter to - this value can be a combined value of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md).

### isLatestOverlappingEnabled

Checks if the latest overlapping filter is on for the specified result item type(s).

```dart
Future<bool> isLatestOverlappingEnabled(int type)
```

**Remarks**

`type` is a bitmask representing the result item types to apply the filter to - this value can be a combined value of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md).

### isResultCrossVerificationEnabled

Checks if the cross verification filter is on for the specified result item type(s).

```dart
Future<bool> isResultCrossVerificationEnabled(int type)
```

**Remarks**

`type` is a bitmask representing the result item types to apply the filter to - this value can be a combined value of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md).

### isResultDeduplicationEnabled

Checks if the deduplication filter is on for the specified result item type(s).

```dart
Future<bool> isResultDeduplicationEnabled(int type)
```

**Remarks**

`type` is a bitmask representing the result item types to apply the filter to - this value can be a combined value of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md).

### setDuplicateForgetTime

Defines the amount of time, in *milliseconds*, that the deduplication filter takes effect for the specified result item type(s). During this time, the library will not scan a certain barcode for the specified time after it has been scanned successfully for the first time.

```dart
Future<void> setDuplicateForgetTime(int resultItemTypes, int time)
```

**Remarks**

`resultItemTypes` is a bitmask representing the result item types to apply the filter to - this value can be a combined value of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md). `time` specifies the target time in *milliseconds*.


Sets the maximum number of overlapping frames to check when the latest overlap filter is on for the specified result item type(s).

```dart
Future<void> setMaxOverlappingFrames(int resultItemTypes, int maxFramesToCheck)
```

**Remarks**

`resultItemTypes` is a bitmask representing the result item types to apply the filter to - this value can be a combined value of [`EnumCapturedResultItemType`](../enum/captured-result-item-type.md). `maxFramesToCheck` specifies the target number of frames that the filter should not exceed.

## Code Snippet

```dart
final MultiFrameResultCrossFilter _multiFilter = MultiFrameResultCrossFilter();
_multiFilter.enableResultCrossVerification(EnumCapturedResultItemType.barcode.value, true);
_multiFilter.enableResultDeduplication(EnumCapturedResultItemType.barcode.value, true);
_multiFilter.enableLatestOverlapping(EnumCapturedResultItemType.barcode.value, true);
_multiFilter.setMaxOverlappingFrames(EnumCapturedResultItemType.barcode.value, 5);
_multiFilter.setDuplicateForgetTime(EnumCapturedResultItemType.barcode.value, 5000);
_cvr.addResultFilter(_multiFilter);
```