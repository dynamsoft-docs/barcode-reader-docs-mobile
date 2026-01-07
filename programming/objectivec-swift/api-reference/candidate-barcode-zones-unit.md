---
layout: default-layout
title: DSCandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSCandidateBarcodeZonesUnit class of Dynamsoft Barcode Reader iOS represents a unit that contains candidate barcode zones unit. It inherits from the DSIntermediateResultUnit class.
keywords: candidate barcode zone, DSCandidateBarcodeZonesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSCandidateBarcodeZonesUnit
permalink: /programming/objectivec-swift/api-reference/candidate-barcode-zones-unit.html
---

# DSCandidateBarcodeZonesUnit Class

`DSCandidateBarcodeZonesUnit` extends the [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which contains a candidate barcode zone.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`getCandidateBarcodeZones`](#getcandidatebarcodezones) | Returns the candidate barcode zones. |
| [`getCount`](#getcount) | Returns the number of candidate barcode zones. |
| [`getCandidateBarcodeZone`](#getcandidatebarcodezone) | Returns a candidate barcode zone. |
| [`removeAllCandidateBarcodeZones`](#removeallcandidatebarcodezones) | Removes all candidate barcode zones. |
| [`removeCandidateBarcodeZone`](#removecandidatebarcodezone) | Removes a candidate barcode zone. |
| [`addCandidateBarcodeZone`](#addcandidatebarcodezone) | Adds a candidate barcode zone. |
| [`setCandidateBarcodeZone`](#setcandidatebarcodezone) | Sets a candidate barcode zone. |

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getCandidateBarcodeZones

Returns the candidate barcode zones as an array of [`DSCandidateBarcodeZone`](candidate-barcode-zone.md) items.

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

An array of [`DSCandidateBarcodeZone`](candidate-barcode-zone.md) items.

### getCount

Returns the number of candidate barcode zones.

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

Returns the [`DSCandidateBarcodeZone`](candidate-barcode-zone.md) from the full array of candidate barcode zone(s) as specified by the index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable DSCandidateBarcodeZone *)getCandidateBarcodeZone:(NSInteger)index;
```
2. 
```swift
func getCandidateBarcodeZone(index: Int) -> CandidateBarcodeZone?
```

**Parameters**

`index`: The index of the candidate barcode zone.

**Return Value**

A [`DSCandidateBarcodeZone`](candidate-barcode-zone.md) object.

### removeAllCandidateBarcodeZones

Removes all of the candidate barcode zones.

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

Removes the [`DSCandidateBarcodeZone`](candidate-barcode-zone.md) at the specified index.

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

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### addCandidateBarcodeZone

Adds a [`CandidateBarcodeZone`](candidate-barcode-zone.md) to the candidate barcode zones array.

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

`matrixToOriginalImage`: The `CGAffineTransform` transformation matrix of the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### setCandidateBarcodeZone

Sets the [`CandidateBarcodeZone`](candidate-barcode-zone.md) at the specified index.

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

`matrixToOriginalImage`: The `CGAffineTransfrom` transformation matrix of the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
