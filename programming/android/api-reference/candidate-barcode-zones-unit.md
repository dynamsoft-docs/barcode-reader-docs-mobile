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

The `CandidateBarcodeZonesUnit` class represents a unit that contains candidate barcode zones unit. It inherits from the `IntermediateResultUnit` class.

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

### getCandidateBarcodeZones

```java
Quadrilateral[] getCandidateBarcodeZones()
```
