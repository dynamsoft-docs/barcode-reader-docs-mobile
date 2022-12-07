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

```objc
@interface iContour
```

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`pointsCount`](#pointscount) |  *NSInteger* | The total points count of the contour. |
| [`points`](#points) | [`CGPoint`](auxiliary-iDBRPoint.md) | The points array of the points that surround the barcode area.. |

## pointsCount

The total points count of the contour.

```objc
@property (nonatomic, assign) NSInteger pointsCount
```  
  
## points

The points array.

```objc
@property (nonatomic, nonnull) NSArray* points
```  
