---
layout: default-layout
title: DSLocalizedBarcodesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: The DSLocalizedBarcodesUnit class represents a unit that contains localized barcodes unit. It inherits from the DSIntermediateResultUnit class.
keywords: GetCount, GetLocalizedBarcode, DSLocalizedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSLocalizedBarcodesUnit
permalink: /programming/objectivec-swift/api-reference/localized-barcodes-unit.html
---

# DSLocalizedBarcodesUnit Class

The `DSLocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSLocalizedBarcodesUnit: DSIntermediateResultUnit
```
2. 
```swift
class LocalizedBarcodesUnit : DSIntermediateResultUnit
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getLocalizedBarcodes`](#getlocalizedbarcodes) | Get all localized barcodes. |
| [`getCount`](#getcount) | Get the count of localized barcodes. |
| [`getLocalizedBarcode`](#getlocalizedbarcode) | Get a localized barcode by index. |
| [`removeAllLocalizedBarcodes`](#removealllocalizedbarcodes) | Remove all localized barcodes. |
| [`removeLocalizedBarcode`](#removelocalizedbarcode) | Remove a localized barcode by index. |
| [`addLocalizedBarcode`](#addlocalizedbarcode) | Add a localized barcode. |
| [`setLocalizedBarcode`](#setlocalizedbarcode) | Set a localized barcode. |

## Inherited Methods

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getLocalizedBarcodes

Get all localized barcodes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (nullable NSArray<DSLocalizedBarcodeElement *> *)getLocalizedBarcodes
```
2. 
```swift
func getLocalizedBarcodes() -> [LocalizedBarcodeElement]?
```

**Return Value**

An array of `LocalizedBarcodeElement` as the localized barcodes.

### getCount

Get the count of localized barcodes.

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
func getCount() -> Int
```

**Return Value**

The count of localized barcodes.

### getLocalizedBarcode

Get the `LocalizeBarcodeElement` at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DSLocalizedBarcodeElement *)getLocalizedBarcode:(NSInteger)index
```
2. 
```swift
func getLocalizedBarcode(_ index: Int) -> LocalizedBarcodeElement?
```

**Parameters**

`[in] index`: The index of the localized barcode.

**Return Value**

The `LocalizeBarcodeElement` at the specified index.

### removeAllLocalizedBarcodes

Remove all localized barcodes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)removeAllLocalizedBarcodes
```
2. 
```swift
func removeAllLocalizedBarcodes()
```

### removeLocalizedBarcode

Remove the `LocalizedBarcodeElement` from the unit at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)removeLocalizedBarcode:(NSInteger)index
```
2. 
```swift
func removeLocalizedBarcode(_ index: Int)
```

**Parameters**

`[in] index`: The index of the localized barcode.

### addLocalizedBarcode

Add a new `LocalizedBarcodeElement` to the unit.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)addLocalizedBarcode:(DSLocalizedBarcodeElement*)element
          matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func addLocalizedBarcode(_ element: LocalizedBarcodeElement, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] element`: The `LocalizedBarcodeElement` to add.

`[in] matrixToOriginalImage`: The transformation matrix from the original image to the unit.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setLocalizedBarcode

Set the `LocalizedBarcodeElement` at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setLocalizedBarcode:(NSInteger)index
                        element:(DSLocalizedBarcodeElement*)element
          matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func setLocalizedBarcode(_ index: Int, element: LocalizedBarcodeElement, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] index`: The index of the localized barcode.

`[in] element`: The `LocalizedBarcodeElement` to set.

`[in] matrixToOriginalImage`: The transformation matrix from the original image to the unit.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
