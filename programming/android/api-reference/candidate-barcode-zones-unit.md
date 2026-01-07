---
layout: default-layout
title: CandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader Android Edition
description: CandidateBarcodeZonesUnit class of Dynamsoft Barcode Reader Android represents a unit that contains candidate barcode zones unit. It inherits from the IntermediateResultUnit class.
keywords: candidate barcode zone, CandidateBarcodeZonesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: CandidateBarcodeZonesUnit
permalink: /programming/android/api-reference/candidate-barcode-zones-unit.html
---

# CandidateBarcodeZonesUnit Class

`CandidateBarcodeZonesUnit` extends the [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which contains a candidate barcode zone.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class CandidateBarcodeZonesUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getCandidateBarcodeZones`](#getcandidatebarcodezones) | Returns the candidate barcode zones. |
| [`getCount`](#getcount) | Returns the number of candidate barcode zones. |
| [`getCandidateBarcodeZone`](#getcandidatebarcodezone) | Returns a candidate barcode zone. |
| [`removeAllCandidateBarcodeZones`](#removeallcandidatebarcodezones) | Removes all candidate barcode zones. |
| [`removeCandidateBarcodeZone`](#removecandidatebarcodezone) | Removes a candidate barcode zone. |
| [`addCandidateBarcodeZone`](#addcandidatebarcodezone) | Adds a candidate barcode zone. |
| [`setCandidateBarcodeZone`](#setcandidatebarcodezone) | Sets a candidate barcode zone. |

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getCandidateBarcodeZones

Returns the candidate barcode zones as an array of [`CandidateBarcodeZone`](candidate-barcode-zone.md) items.

```java
CandidateBarcodeZone[] getCandidateBarcodeZones()
```

**Return Value**

An array of [`CandidateBarcodeZone`](candidate-barcode-zone.md) items.
### getCount

Returns the number of candidate barcode zones.

```java
int getCount()
```

**Return Value**

The number of candidate barcode zones.

### getCandidateBarcodeZone

Returns the [`CandidateBarcodeZone`](candidate-barcode-zone.md) from the full array of candidate barcode zone(s) as specified by the index.

```java
CandidateBarcodeZone getCandidateBarcodeZone(int index)
```

**Parameters**

`[in] index`: The index of the candidate barcode zone.

**Return Value**

A [`CandidateBarcodeZone`](candidate-barcode-zone.md) object.

### removeAllCandidateBarcodeZones

Removes all of the candidate barcode zones.

```java
void removeAllCandidateBarcodeZones()
```

### removeCandidateBarcodeZone

Removes the [`CandidateBarcodeZone`](candidate-barcode-zone.md) at the specified index.

```java
int removeCandidateBarcodeZone(int index)
```

**Parameters**

`[in] index`: The index of the candidate barcode zone.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### addCandidateBarcodeZone

Adds a [`CandidateBarcodeZone`](candidate-barcode-zone.md) to the candidate barcode zones array.

```java
int addCandidateBarcodeZone(CandidateBarcodeZone barcodeZone, Matrix matrixToOriginalImage)
```

**Parameters**

`[in] barcodeZone`: The `CandidateBarcodeZone` to be added.

`[in] matrixToOriginalImage`: The transformation `Matrix` of the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### setCandidateBarcodeZone

Sets the [`CandidateBarcodeZone`](candidate-barcode-zone.md) at the specified index.

```java
int setCandidateBarcodeZone(int index, CandidateBarcodeZone barcodeZone, Matrix matrixToOriginalImage)
```

**Parameters**

`[in] index`: The index where the new candidate barcode zone will be added.

`[in] barcodeZone`: The `CandidateBarcodeZone` to be set.

`[in] matrixToOriginalImage`: The transformation `Matrix` of the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
