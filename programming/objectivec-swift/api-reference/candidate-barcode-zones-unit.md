---
layout: default-layout
title: DSCandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSCandidateBarcodeZonesUnit class represents a unit that contains candidate barcode zones unit. It inherits from the DSIntermediateResultUnit class.
keywords: candidate barcode zone, DSCandidateBarcodeZonesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSCandidateBarcodeZonesUnit
permalink: /programming/objectivec-swift/api-reference/candidate-barcode-zones-unit.html
---

# DSCandidateBarcodeZonesUnit Class

The `DSCandidateBarcodeZonesUnit` class represents a unit that contains candidate barcode zones unit. It inherits from the `DSIntermediateResultUnit` class.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSCandidateBarcodeZonesUnit : DSIntermediateResultUnit
```
2. 
```swift
class CandidateBarcodeZonesUnit : IntermediateResultUnit
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`candidateBarcodeZones`](#candidatebarcodezones) | *NSArray<DSQuadrilateral\*> \** |An array of quadrilaterals that indicates the barcode zones. |

### candidateBarcodeZones

An array of quadrilaterals that indicates the barcode zones.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, copy, nullable) NSArray<DSQuadrilateral *> *candidateBarcodeZones;
```
2. 
```swift
var candidateBarcodeZones: [DSQuadrilateral]? { get set }
```
