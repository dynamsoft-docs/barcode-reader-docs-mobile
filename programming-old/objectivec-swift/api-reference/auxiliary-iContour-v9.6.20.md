---
layout: default-layout
title: iContour Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iContour Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iContour, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iContour-v9.6.20.html
---


# Class iContour

The iContour is one of the [`results`](auxiliary-iIntermediateResult.html#results) type in `iIntermediateResult`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iContour : NSObject
```
2. 
```swift
class iContour : NSObject
```

| Attribute | Description |
|---------- | ----------- |
| [`pointsCount`](#pointscount) | The total points count of the contour. |
| [`points`](#points) | The points array of the points that surround the barcode area.. |

## pointsCount

The total points count of the contour.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger pointsCount
```
2. 
```swift
var pointsCount: Int { get set }
```

## points

The points array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nonnull) NSArray* points
```
2. 
```swift
var points: [Any] { get set }
```
