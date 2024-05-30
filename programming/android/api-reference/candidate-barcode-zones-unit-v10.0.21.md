---
layout: default-layout
title: CandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader Android Edition
description: CandidateBarcodeZonesUnit class represents a unit that contains candidate barcode zones unit. It inherits from the IntermediateResultUnit class.
keywords: candidate barcode zone, CandidateBarcodeZonesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: CandidateBarcodeZonesUnit
permalink: /programming/android/api-reference/candidate-barcode-zones-unit-v10.0.21.html
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

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

| Method | Description |
|------- |-------------|
| [`clone`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |
| [`gethashId`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gethashid) | Gets the hash ID of the unit. |
| [`getOriginalImageHashId`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagehashid) | Gets the hash ID of the original image. You can use this ID to get the original image via [`IntermediateResultManager`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-manager.html) class. |
| [`getOriginalImageTag`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagetag) | Gets the image tag of the original image. |
| [`getType`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gettype) | Gets the type of the intermediate result unit. |
| [`getTransformMatrix`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`EnumTransformMatrixType`]({{site.dcv_enumerations}}core/transform-matrix-type.html). |

### getCandidateBarcodeZones

```java
Quadrilateral[] getCandidateBarcodeZones()
```
