---
layout: default-layout
title: iSamplingImageData Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iSamplingImageData Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iSamplingImageData, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
ignore: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iSamplingImageData.html
---

# Class iSamplingImageData

`SamplingImageData` stores the detailed image data in `ExtendedResult`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iSamplingImageData : NSObject
```
2. 
```swift
class iSamplingImageData : NSObject
```

| Attribute | Descriptions |
|---------- | ------------ |
| [`bytes`](#bytes) | The sampling image data in a byte array. |
| [`width`](#width) | The width of the sampling image. |
| [`height`](#height) | The height of the sampling image. |

## bytes

The sampling image data in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSData* bytes;
```
2. 
```swift
var bytes: Data? { get set }
```

## width

The width of the sampling image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSInteger width;
```
2. 
```swift
var width: Int { get set }
```

## height

The height of the sampling image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSInteger height;
```
2. 
```swift
var height: Int { get set }
```
