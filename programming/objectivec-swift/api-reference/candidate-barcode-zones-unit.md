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

The `DSCandidateBarcodeZonesUnit` class represents a unit that contains candidate barcode zones unit. It inherits from the [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) class.

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

## Inherited Attributes

The following attributes are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`hashId`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#hashid) | *NSString \** | The hash ID of the unit. |
| [`originalImageHashId`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#originalimagehashid) | *NSString \** | The hash ID of the original image. You can use this ID to get the original image via [`DSIntermediateResultManager`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-manager.html) class. |
| [`originalImageTag`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#originalimagetag) | *DSImageTag \** | The image tag of the original image. |
| [`type`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#type) | *DSIntermediateResultUnitType* | The type of the intermediate result unit. |

## Inherited Methods

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

| Method | Description |
|------- |-------------|
| [`getTransformMatrix`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`DSTransformMatrixType`]({{site.enums}}core/transform-matrix-type.html). |
| [`clone`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |

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
