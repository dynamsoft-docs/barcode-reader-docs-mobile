---
layout: default-layout
title: DSDecodedBarcodesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSDecodedBarcodesUnit class represents a unit that contains decoded barcode elements. It inherits from the DSIntermediateResultUnit class.
keywords: GetCount, GetDecodedBarcode, DSDecodedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDecodedBarcodesUnit
permalink: /programming/objectivec-swift/api-reference/decoded-barcodes-unit.html
---

# DSDecodedBarcodesUnit Class

The `DSDecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NS_SWIFT_NAME(DecodedBarcodesUnit)
@interface DSDecodedBarcodesUnit: DSIntermediateResultUnit
```
2. 
```swift
class DecodedBarcodesUnit: DSIntermediateResultUnit
```

## Methods

| Method | Description |
|------- |-------------|
| [`getDecodedBarcodes`](#getdecodedbarcodes) | Get all the barcodes that are decoded from the image. |
| [`getCount`](#getcount) | Get the number of decoded barcodes. |
| [`getDecodedBarcode`](#getdecodedbarcode) | Get the decoded barcode by specifying the index. |
| [`removeAllDecodedBarcodes`](#removealldecodedbarcodes) | Remove all the decoded barcodes. |
| [`setDecodedBarcode`](#setdecodedbarcode) | Set the decoded barcode. |

## Inherited Methods

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/region-object-element-ios.md -%}

### getDecodedBarcodes

Get all the barcodes that are decoded from the image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (nullable NSArray<DSDecodedBarcodeElement*>*)getDecodedBarcodes
```
2. 
```swift
func getDecodedBarcodes() -> [DSDecodedBarcodeElement]?
```

**Return Value**

An array of `DSDecodedBarcodeElement` as the decoded barcodes.

### getCount

Get the number of decoded barcodes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)getCount
```
2. 
```swift
func getCount() -> NSInteger
```

**Return Value**

The number of decoded barcodes.

### getDecodedBarcode

Get the `DSDecodedBarcodeElement` object at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (nullable DSDecodedBarcodeElement*)getDecodedBarcode:(NSInteger)index
```
2. 
```swift
func getDecodedBarcode(index: NSInteger) -> DSDecodedBarcodeElement?
```

**Parameters**

`[in] index`: The index of the decoded barcode.

**Return Value**

A `DSDecodedBarcodeElement` object as the decoded barcode object at the specified index.

### removeAllDecodedBarcodes

Remove all the `DSDecodedBarcodeElement` of the unit.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)removeAllDecodedBarcodes
```
2. 
```swift
func removeAllDecodedBarcodes()
```

### setDecodedBarcode

Set the `DSDecodedBarcodeElement` object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)setDecodedBarcode:(DSDecodedBarcodeElement*)element
         matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage
```
2. 
```swift
func setDecodedBarcode(element: DSDecodedBarcodeElement, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] element`: The decoded barcode object to be set.

`[in] matrixToOriginalImage`: The matrix to convert the decoded barcode object to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
