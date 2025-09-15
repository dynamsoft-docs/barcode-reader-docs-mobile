---
layout: default-layout
title: Common Classes - Dynamsoft Barcode Reader iOS API Reference
description: The common classes of Dynamsoft Barcode Reader SDK iOS edition such as point, quadrilateral, & region definition.
keywords: Common Classes, API reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-common-classes-v9.6.20.html
---

# Common Classes

## [iQuadrilateral](auxiliary-iQuadrilateral.html)

This class stores the quadrilateral points data.

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
class iQuadrilateral : NSObject
```

| Attribute | Descriptions |
|---------- | ------------ |
| [`points`](auxiliary-iQuadrilateral.html#points) | Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex. |

## [iRegionDefinition](auxiliary-iRegionDefinition.html)

This class stores the region data. You can make settings on the scan region through this class.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iRegionDefinition : NSObject
```
2. 
```swift
class iRegionDefinition : NSObject
```

| Attribute | Descriptions |
|---------- | ------------ |
| [`regionTop`](auxiliary-iRegionDefinition.html#regiontop) | The top-most coordinate or percentage of the region. |
| [`regionLeft`](auxiliary-iRegionDefinition.html#regionleft) | The left-most coordinate or percentage of the region. |
| [`regionRight`](auxiliary-iRegionDefinition.html#regionright) | The right-most coordinate or percentage of the region. |
| [`regionBottom`](auxiliary-iRegionDefinition.html#regionbottom) | The bottom-most coordinate or percentage of the region. |
| [`regionMeasuredByPercentage`](auxiliary-iRegionDefinition.html#regionmeasuredbypercentage) | Sets whether or not to use percentage to measure the region size. |
