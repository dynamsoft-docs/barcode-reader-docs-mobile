---
layout: default-layout
title: DSExtendedBarcodeResult Class - Dynamsoft Barcode Reader iOS Edition
description: DSExtendedBarcodeResult class of Dynamsoft Barcode Reader iOS represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.
keywords: DSExtendedBarcodeResult, class, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSExtendedBarcodeResult
---


# DSExtendedBarcodeResult

`DSExtendedBarcodeResult` extends the [`DSDecodedBarcodeElement`](decoded-barcode-element.md) class and represents extended information about a barcode result.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSExtendedBarcodeResult: DSDecodedBarcodeElement
```
2. 
```swift
class ExtendedBarcodeResult: DecodedBarcodeElement
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getExtendedBarcodeResultType`](#getextendedbarcoderesulttype) | Returns the type of the extended barcode result. |
| [`getDeformation`](#getdeformation) | Returns the deformation level of the barcode zone. |
| [`getClarity`](#getclarity) | Returns the clarity score of the barcode zone. |
| [`getSamplingImage`](#getsamplingimage) | Returns the sampling image of the barcode zone. |

The following methods are inherited from class [`DecodedBarcodeElement`](decoded-barcode-element.md).

| Methods | Description |
| ------- | ----------- |
| [`init`](decoded-barcode-element.md#init) | Initialize a new `DSDecodedBarcodeElement` object. |
| [`getText`](decoded-barcode-element.md#gettext) | Returns the text of the decoded barcode. |
| [`setText`](decoded-barcode-element.md#settext) | Set the text of the decoded barcode. |
| [`getBytes`](decoded-barcode-element.md#getbytes) | Returns the raw bytes of the decoded barcode. |
| [`setBytes`](decoded-barcode-element.md#setbytes) | Set the raw bytes of the decoded barcode. |
| [`getFormat`](decoded-barcode-element.md#getformat) | Returns the format of the decoded barcode. |
| [`setFormat`](decoded-barcode-element.md#setformat) | Set the format of the decoded barcode. |
| [`getConfidence`](decoded-barcode-element.md#getconfidence) | Returns the confidence score of the decoded barcode. |
| [`setConfidence`](decoded-barcode-element.md#setconfidence) | Set the confidence of the decoded barcode. |
| [`getFormatString`](decoded-barcode-element.md#getformatstring) | Returns the format string of the decoded barcode. |
| [`getAngle`](decoded-barcode-element.md#getangle) | Returns the orientation angle of the decoded barcode. |
| [`getModuleSize`](decoded-barcode-element.md#getmodulesize) | Returns the module size of the decoded barcode. |
| [`getDetails`](decoded-barcode-element.md#getdetails) | Returns the `DSBarcodeDetails` of the decoded barcode. |
| [`getExtendedBarcodeResults`](decoded-barcode-element.md#getextendedbarcoderesults) | Returns the extended barcode results of the decoded barcode. |
| [`isDPM`](decoded-barcode-element.md#isdpm) | Specifies if the decoded barcode is a DPM code or not. |
| [`isMirrored`](decoded-barcode-element.md#ismirrored) | Specifies if the decoded barcode is mirrored or not. |

The following attributes are inherited from class [`DSRegionObjectElement`]({{ site.dcvb_ios_api }}core/intermediate-results/region-object-element.html).

| Method | Description |
|------- |-------------|
| [`getLocation`]({{ site.dcvb_ios_api }}core/intermediate-results/region-object-element.html#getlocation) | Gets the location of the region object, represented as a quadrilateral. |
| [`setLocation`]({{ site.dcvb_ios_api }}core/intermediate-results/region-object-element.html#setlocation) | Sets the location of the region object. |
| [`getReferencedElement`]({{ site.dcvb_ios_api }}core/intermediate-results/region-object-element.html#getreferencedelement) | Gets the referenced element that supports the capturing of this element. |
| [`getRegionObjectElementType`]({{ site.dcvb_ios_api }}core/intermediate-results/region-object-element.html#getregionobjectelementtype) | Gets the type of the region object element, defined by the enumeration [`DSRegionObjectElementType`]({{ site.dcvb_android_api }}core/enum/region-object-element-type.html?lang=objc,swift). |

### getExtendedBarcodeResultType

Returns the type of the extended barcode result as a [`DSExtendedBarcodeResultType`]({{ site.dcvb_ios_api }}core/enum//extended-barcode-result-type.html?lang=objc,swift) enumeration item.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DSExtendedBarcodeResultType)getExtendedBarcodeResultType;
```
2. 
```swift
func getExtendedBarcodeResultType() -> DSExtendedBarcodeResultType
```

**Return Value**

A [`DSExtendedBarcodeResultType`]({{ site.dcvb_ios_api }}core/enum//extended-barcode-result-type.html?lang=objc,swift) item representing the extended barcode result type.

### getDeformation

Returns the degree of deformation or distortion of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)getDeformation;
```
2. 
```swift
func getDeformation() -> Int
```

**Return Value**

An integer representing the deformation level of the barcode zone.

### getClarity

Returns the clarity/quality level of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)getClarity;
```
2. 
```swift
func getClarity() -> Int
```

**Return Value**

An integer representing the clarity/quality level of the barcode zone.

### getSamplingImage

Returns the sampling image of the decoded barcode as a [`DSImageData`]({{ site.dcvb_ios_api }}core/basic-structures/image-data.html) object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (nullable DSImageData *)getSamplingImage;
```
2. 
```swift
func getSamplingImage() -> DSImageData?
```

**Return Value**

A `DSImageData` object representing the sampling image of the barcode zone.
