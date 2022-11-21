---
layout: default-layout
title: Dynamsoft Barcode Reader Objective-C & Swift API Reference - iImageData Class
description: This page shows the iImageData Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iImageData, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iImageData.html
---


# Class iImageData

Stores the image data.  

```objc
@interface iImageData
```

| Method | Description |
| ------ | ----------- |
| [`toUIImage`](#touiimage) | Convert the `ImageData` to a `UIImage`. |

## toUIImage

Convert the `iImageData` to an `UIImage`.

```objc
- (UIImage * _Nullable)toUIImage:(NSError *_Nullable *_Nullable)error;
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
var image = try? imageData.toUIImage()
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

```objc
@property (nonatomic, nonnull) NSData* bytes;
```

## width

The width of the image in pixels.  

```objc
@property (nonatomic, assign) NSInteger width
```

## height

The height of the image in pixels.  

```objc
@property (nonatomic, assign) NSInteger height
```

## stride

The stride (or scan width) of the image.

```objc
@property (nonatomic, assign) NSInteger stride
```

## format

The image pixel format used in the image byte array.

```objc
@property (nonatomic, assign) EnumImagePixelFormat format
```

## orientation

The orientation of the image. It can be 0, 90, 180, or 270 based on the device orientation.

```objc
@property (nonatomic, assign) NSInteger orientation
```
