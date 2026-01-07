---
layout: default-layout
title: DSLocalizedBarcodesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: The DSLocalizedBarcodesUnit class of Dynamsoft Barcode Reader iOS represents a unit that contains localized barcodes unit. It inherits from the DSIntermediateResultUnit class.
keywords: GetCount, GetLocalizedBarcode, DSLocalizedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSLocalizedBarcodesUnit
permalink: /programming/objectivec-swift/api-reference/localized-barcodes-unit.html
---

# DSLocalizedBarcodesUnit Class

`DSLocalizedBarcodesUnit` extends the [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which contains localized barcodes.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`getLocalizedBarcodes`](#getlocalizedbarcodes) | Returns an array of `LocalizedBarcodeElement`. |
| [`getCount`](#getcount) | Returns the number of localized barcodes in the unit. |
| [`getLocalizedBarcode`](#getlocalizedbarcode) | Returns the `LocalizedBarcodeElement` at the specified index. |
| [`removeAllLocalizedBarcodes`](#removealllocalizedbarcodes) | Removes all the localized barcodes in the unit. |
| [`removeLocalizedBarcode`](#removelocalizedbarcode) | Removes the `LocalizedBarcodeElement` at the specified index from the unit. |
| [`addLocalizedBarcode`](#addlocalizedbarcode) | Add a new `LocalizedBarcodeElement` to the unit. |
| [`setLocalizedBarcode`](#setlocalizedbarcode) | Set a `LocalizedBarcodeElement` at the specified index. |

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getLocalizedBarcodes

Returns an array of [`LocalizedBarcodeElement`](localized-barcode-element.md), which contains the detailed information for each localized barcode.

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

**Return value**

An array of `LocalizedBarcodeElement`, which contains the detailed information for each localized barcode.

### getCount

Returns the number of localized barcodes ([`LocalizedBarcodeElement`](localized-barcode-element.md)) in the unit.

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

The number of localized barcodes.

### getLocalizedBarcode

Returns the [`LocalizedBarcodeElement`](localized-barcode-element.md) at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (nullable DSLocalizedBarcodeElement *)getLocalizedBarcode:(NSInteger)index
```
2. 
```swift
func getLocalizedBarcode(_ index: Int) -> LocalizedBarcodeElement?
```

**Parameters**

`[in] index`: The index of the localized barcode.

**Return value**

The [`LocalizedBarcodeElement`](localized-barcode-element.md) at the specified index.

### removeAllLocalizedBarcodes

Removes all the localized barcodes in the unit.

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

Removes the [`LocalizedBarcodeElement`](localized-barcode-element.md) at the specified index from the unit.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)removeLocalizedBarcode:(NSInteger)index
```
2. 
```swift
func removeLocalizedBarcode(_ index: Int) -> Int
```

**Parameters**

`[in] index`: The index of the localized barcode element.

### addLocalizedBarcode

Add a new [`LocalizedBarcodeElement`](localized-barcode-element.md) to the unit.

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

`[in] element`: The `LocalizedBarcodeElement` to be added.

`[in] matrixToOriginalImage`: The `CGAffineTransform` transformation matrix of the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### setLocalizedBarcode

Set a [`LocalizedBarcodeElement`](localized-barcode-element.md) at the specified index.

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

`[in] index`: The index where the localized barcode element will be set.

`[in] element`: The `LocalizedBarcodeElement` to be set.

`[in] matrixToOriginalImage`: The `CGAffineTransform` transformation matrix of the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
