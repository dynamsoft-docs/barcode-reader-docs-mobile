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

The `CandidateBarcodeZone` class represents the information of a single candidate barcode zone. It records the location as well as the possible barcode formats of the barcode in the zone.

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
| [`possibleFormats`](#possibleformats) | The possible barcode formats of the barcode in the zone. |

### location

The location of the candidate barcode zone.

```java
Quadrilateral location;
```

### possibleFormats

The possible formats of the candidate barcode zone.

```java
long possibleFormats;
```
