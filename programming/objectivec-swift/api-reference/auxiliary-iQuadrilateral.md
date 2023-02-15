---
layout: default-layout
title: iQuadrilateral Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iQuadrilateral Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iQuadrilateral, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iQuadrilateral.html
---


# Class iQuadrilateral

Stores the quadrilateral.  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iQuadrilateral : NSObject
```
2. 
```swift
var endPoint: Int { get set }
```

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`points`](#points) | *NSArray\** | Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex. |

## points

Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nonnull) NSArray* points;
```
2. 
```swift
var points: [Any]? { get set }
```
