---
layout: default-layout
title: Dynamsoft Barcode Reader Objective-C & Swift API Reference - iImageData Class
description: This page shows the iImageData Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iImageData, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
---


# Class iImageData

Stores the image data.  

```objc
@interface iImageData
```

| Method | Type | Descriptions |
|---------- | ---- | ----------- |
| [`toUIImage`](#touiimage) | -- | Convert the ImageData to a UIImage. |
| [`bytesLength`](#byteslength) | *NSInteger* | The length of the image data byte array. |
| [`bytes`](#bytes) | *unsigned char\** | The image data content in a byte array. |
| [`width`](#width) | *NSInteger* | The width of the image in pixels. |
| [`height`](#height) | *NSInteger* | The height of the image in pixels. |
| [`stride`](#stride) | *NSInteger* | The stride (or scan width) of the image. |
| [`format`](#format) | [`EnumImagePixelFormat`]({{ site.enumerations }}other-enums.html#imagepixelformat) | The image pixel format used in the image byte array. |

## toUIImage

Convert the iImageData to an UIImage.

```objc
- (UIImage * _Nullable)toUIImage:(NSError *_Nullable *_Nullable)error;
```

**Return Value**

An UIImage that converted from the iImageData.

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

## bytesLength

The length of the image data byte array.

```objc
NSInteger bytesLength
```

## bytes

The image data content in a byte array.

```objc
unsigned char* bytes
```

## width

The width of the image in pixels.  

```objc
NSInteger width
```

## height

The height of the image in pixels.  

```objc
NSInteger height
```

## stride

The stride (or scan width) of the image.

```objc
NSInteger stride
```

## format

The image pixel format used in the image byte array.

```objc
EnumImagePixelFormat format
```

## orientation

The orientation of the image. It can be 0, 90, 180, or 270 based on the device orientation.

```objc
NSInteger orientation
```
