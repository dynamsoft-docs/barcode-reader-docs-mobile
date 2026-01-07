---
layout: default-layout
title: DSDecodedBarcodesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSDecodedBarcodesUnit class of Dynamsoft Barcode Reader iOS represents a unit that contains decoded barcode elements. It inherits from the DSIntermediateResultUnit class.
keywords: GetCount, GetDecodedBarcode, DSDecodedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDecodedBarcodesUnit
permalink: /programming/objectivec-swift/api-reference/decoded-barcodes-unit.html
---

# DSDecodedBarcodesUnit Class

`DSDecodedBarcodesUnit` extends the [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which holds the decoded barcodes.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`getDecodedBarcodes`](#getdecodedbarcodes) | Returns all the barcodes that are decoded from the image. |
| [`getCount`](#getcount) | Returns the number of decoded barcodes. |
| [`getDecodedBarcode`](#getdecodedbarcode) | Returns the decoded barcode by specifying the index. |
| [`removeAllDecodedBarcodes`](#removealldecodedbarcodes) | Remove all the decoded barcodes. |
| [`setDecodedBarcode`](#setdecodedbarcode) | Set the decoded barcode. |

The following methods are inherited from [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/region-object-element-ios.md -%}

### getDecodedBarcodes

Returns all the barcodes that are decoded from the image as an array of [`DSDecodedBarcodeElement`](decoded-barcode-element.md).

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

An array of [`DSDecodedBarcodeElement`](decoded-barcode-element.md) as the decoded barcodes.

### getCount

Returns the number of barcodes that are decoded from the image.

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

An integer representing the number of barcodes that are decoded from the image.

### getDecodedBarcode

Returns the [`DSDecodedBarcodeElement`](decoded-barcode-element.md) at the specified index. This is the same as accessing the same index of the result array from [`getDecodedBarcodes`](#getdecodedbarcodes).

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

`[in] index`: The index of the decoded barcode from the array of decoded barcodes.

**Return Value**

A [`DSDecodedBarcodeElement`](decoded-barcode-element.md) representing the decoded barcode.

### removeAllDecodedBarcodes

Removes all the [`DSDecodedBarcodeElement`](decoded-barcode-element.md) from the `DSDecodedBarcodesUnit`.

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

Set the [`DSDecodedBarcodeElement`](decoded-barcode-element.md) of the `DSDecodedBarcodesUnit`.

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

`[in] element`: The `DSDecodedBarcodeElement` to replace all the decoded barcodes of the `DSDecodedBarcodesUnit`.

`[in] matrixToOriginalImage`: The transformation matrix to convert the decoded barcode object to the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
