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

## Methods

| Method | Description |
|------- |-------------|
| [`getCandidateBarcodeZones`](#getcandidatebarcodezones) | Gets the candidate barcode zones. |
| [`getCount`](#getcount) | Gets the number of candidate barcode zones. |
| [`getCandidateBarcodeZone`](#getcandidatebarcodezone) |  Gets the candidate barcode zone. |
| [`removeAllCandidateBarcodeZones`](#removeallcandidatebarcodezones) | Removes all candidate barcode zones. |
| [`removeCandidateBarcodeZone`](#removecandidatebarcodezone) | Removes the candidate barcode zone. |
| [`addCandidateBarcodeZone`](#addcandidatebarcodezone) | Adds the candidate barcode zone. |
| [`setCandidateBarcodeZone`](#setcandidatebarcodezone) | Sets the candidate barcode zone. |

## Inherited Methods

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getCandidateBarcodeZones

Gets the candidate barcode zones.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable NSArray< DSCandidateBarcodeZone* >*)getCandidateBarcodeZones;
```
2. 
```swift
func getCandidateBarcodeZones() -> [CandidateBarcodeZone]?
```

**Return Value**

An array of `DSCandidateBarcodeZone` objects that represents the candidate barcode zones.

### getCount

Gets the number of candidate barcode zones.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)getCount;
```
2. 
```swift
func getCount() -> Int
```

**Return Value**

The number of candidate barcode zones.

### getCandidateBarcodeZone

Gets the candidate barcode zone.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(DSCandidateBarcodeZone *)getCandidateBarcodeZone:(NSInteger)index;
```
2. 
```swift
func getCandidateBarcodeZone(index: Int) -> CandidateBarcodeZone?
```

**Parameters**

`index`: The index of the candidate barcode zone.

**Return Value**

A `DSCandidateBarcodeZone` object that represents the candidate barcode zone.

### removeAllCandidateBarcodeZones

Removes all candidate barcode zones.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(void)removeAllCandidateBarcodeZones;
```
2. 
```swift
func removeAllCandidateBarcodeZones()
```

### removeCandidateBarcodeZone

Removes the candidate barcode zone.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)removeCandidateBarcodeZone:(NSInteger)index;
```
2. 
```swift
func removeCandidateBarcodeZone(index: Int) -> Int
```

**Parameters**

`index`: The index of the candidate barcode zone.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### addCandidateBarcodeZone

Adds the candidate barcode zone.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)addCandidateBarcodeZone:(DSCandidateBarcodeZone*)barcodeZone
    matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func addCandidateBarcodeZone(barcodeZone: CandidateBarcodeZone, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`barcodeZone`: The candidate barcode zone to be added.

`matrixToOriginalImage`: The transformation matrix of the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setCandidateBarcodeZone

Sets the candidate barcode zone.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setCandidateBarcodeZone:(NSInteger)index
                        barcodeZone:(DSCandidateBarcodeZone*)barcodeZone
              matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func setCandidateBarcodeZone(index: Int, barcodeZone: CandidateBarcodeZone, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`index`: The index of the candidate barcode zone.

`barcodeZone`: The candidate barcode zone to be set.

`matrixToOriginalImage`: The transformation matrix of the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
