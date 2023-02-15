---
layout: default-layout
title: iContour Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iContour Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iContour, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iContour.html
---


# Class iContour

The iContour is one of the [`results`](auxiliary-iIntermediateResult.md#results) type in `iIntermediateResult`.

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

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`pointsCount`](#pointscount) |  *NSInteger* | The total points count of the contour. |
| [`points`](#points) | [`CGPoint`](auxiliary-iDBRPoint.md) | The points array of the points that surround the barcode area.. |

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
