---
layout: default-layout
title: CandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader Android Edition
description: CandidateBarcodeZonesUnit class represents a unit that contains candidate barcode zones unit. It inherits from the IntermediateResultUnit class.
keywords: candidate barcode zone, CandidateBarcodeZonesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: CandidateBarcodeZonesUnit
permalink: /programming/android/api-reference/candidate-barcode-zones-unit.html
---

# CandidateBarcodeZonesUnit Class

The `CandidateBarcodeZonesUnit` class represents a unit that contains candidate barcode zones unit. It inherits from the [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class CandidateBarcodeZonesUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getCandidateBarcodeZones`](#getcandidatebarcodezones) | Get an array of quadrilaterals as the candidate barcode zones. |
| [`getCount`](#getcount) | Get the number of candidate barcode zones. |
| [`getCandidateBarcodeZone`](#getcandidatebarcodezone) | Get a candidate barcode zone. |
| [`removeAllCandidateBarcodeZones`](#removeallcandidatebarcodezones) | Remove all candidate barcode zones. |
| [`removeCandidateBarcodeZone`](#removecandidatebarcodezone) | Remove a candidate barcode zone. |
| [`addCandidateBarcodeZone`](#addcandidatebarcodezone) | Add a candidate barcode zone. |
| [`setCandidateBarcodeZone`](#setcandidatebarcodezone) | Set a candidate barcode zone. |

## Inherited Methods

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getCandidateBarcodeZones

Get an array of `CandidateBarcodeZone` as the candidate barcode zones.

```java
CandidateBarcodeZone[] getCandidateBarcodeZones()
```

### getCount

Get the number of candidate barcode zones.

```java
int getCount()
```

**Return Value**

Returns the number of candidate barcode zones.

### getCandidateBarcodeZone

Get the `CandidateBarcodeZone` at the specified index.

```java
CandidateBarcodeZone getCandidateBarcodeZone(int index)
```

**Parameters**

`[in] index`: The index of the candidate barcode zone.

**Return Value**

Returns the `CandidateBarcodeZone` at the specified index.

### removeAllCandidateBarcodeZones

Remove all candidate barcode zones.

```java
void removeAllCandidateBarcodeZones()
```

### removeCandidateBarcodeZone

Remove the `CandidateBarcodeZone` at the specified index.

```java
int removeCandidateBarcodeZone(int index)
```

**Parameters**

`[in] index`: The index of the candidate barcode zone.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### addCandidateBarcodeZone

Add a `CandidateBarcodeZone` to the candidate barcode zones array.

```java
int addCandidateBarcodeZone(CandidateBarcodeZone barcodeZone, Matrix matrixToOriginalImage)
```

**Parameters**

`[in] barcodeZone`: The `CandidateBarcodeZone` to be added.

`[in] matrixToOriginalImage`: The transformation matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setCandidateBarcodeZone

Set the `CandidateBarcodeZone` at the specified index.

```java
int setCandidateBarcodeZone(int index, CandidateBarcodeZone barcodeZone, Matrix matrixToOriginalImage)
```

**Parameters**

`[in] index`: The index of the candidate barcode zone.

`[in] barcodeZone`: The `CandidateBarcodeZone` to be set.

`[in] matrixToOriginalImage`: The transformation matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
