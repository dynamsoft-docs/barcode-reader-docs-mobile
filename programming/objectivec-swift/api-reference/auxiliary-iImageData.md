---
layout: default-layout
title: iImageData Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iImageData Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iImageData, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iImageData.html
---


# Class iImageData

Stores the image data.  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iImageData : NSObject
```
2. 
```swift
class iImageData : NSObject
```

| Method | Description |
| ------ | ----------- |
| [`toUIImage`](#touiimage) | Convert the `ImageData` to a `UIImage`. |

## toUIImage

Convert the `iImageData` to an `UIImage`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (UIImage * _Nullable)toUIImage:(NSError *_Nullable *_Nullable)error;
```
2. 
```swift
func toUIImage() throws -> UIImage
```

**Return Value**

An `UIImage` that converted from the `iImageData`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError *error;
UIImage *image = [imageData toUIImage:&error];
```
2. 
```swift
do{
   image = try imageData.toUIImage()
} catch{
   // Add your code to deal with exceptions.
}
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`bytes`](#bytes) | *NSData* | The image data content in a byte array. |
| [`width`](#width) | *NSInteger* | The width of the image in pixels. |
| [`height`](#height) | *NSInteger* | The height of the image in pixels. |
| [`stride`](#stride) | *NSInteger* | The stride (or scan width) of the image. |
| [`format`](#format) | [`EnumImagePixelFormat`]({{ site.mobile_enum }}image-pixel-format.html?lang=objc,swift) | The image pixel format used in the image byte array. |

## bytes

The image data content in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nonnull) NSData* bytes;
```
2. 
```swift
var bytes: Data? { get set }
```

## width

The width of the image in pixels.  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger width
```
2. 
```swift
var width: Int { get set }
```

## height

The height of the image in pixels.  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger height
```
2. 
```swift
var height: Int { get set }
```

## stride

The stride (or scan width) of the image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger stride
```
2. 
```swift
var stride: Int { get set }
```

## format

The image pixel format used in the image byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumImagePixelFormat format
```
2. 
```swift
var format: EnumImagePixelFormat { get set }
```

## orientation

The orientation of the image. It can be 0, 90, 180, or 270 based on the device orientation.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger orientation
```
2. 
```swift
var orientation: Int { get set }
```
