---
layout: default-layout
title: CandidateBarcodeZone Class - Dynamsoft Barcode Reader Android Edition
description: CandidateBarcodeZone class of Dynamsoft Barcode Reader Android edition represents the information of a single candidate barcode zone.
keywords: candidate barcode zone, CandidateBarcodeZone, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: CandidateBarcodeZone
---

# CandidateBarcodeZone Class

`CandidateBarcodeZone` is a class that represents the information of a single candidate barcode zone.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class CandidateBarcodeZone
```

## Attributes

| Attribute | Description |
| --------- | ------------|
| [`location`](#location) | The location of the candidate barcode zone. |
| [`possibleFormats`](#possibleformats) | The possible barcode formats of the barcode in the candidate barcode zone. |

### location

The location of the candidate barcode zone within the image represented as a [`Quadrilateral`]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html).

```java
Quadrilateral location;
```

### possibleFormats

The possible format(s) of the barcode in the candidate barcode zone.

```java
long possibleFormats;
```
