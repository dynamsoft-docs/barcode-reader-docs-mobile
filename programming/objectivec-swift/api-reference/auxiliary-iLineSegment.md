---
layout: default-layout
title: iLineSegment Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iLineSegment Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iLineSegment, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iLineSegment.html
---


# Class iLineSegment

Stores line segment data.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iLineSegment : NSObject
```
2. 
```swift
class iLineSegment : NSObject
```


| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`startPoint`](#startpoint) | [`CGPoint`](auxiliary-iDBRPoint.md) | The start point of the line segment. |
| [`endPoint`](#endpoint) | [`CGPoint`](auxiliary-iDBRPoint.md) | The end point of the line segment. |
| [`linesConfidenceCoefficients`](#linesconfidencecoefficients) | *NSData \** | *byte\[\]* | The confidence coefficients for lines. |

## startPoint

The start point of the line segment.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) CGPoint startPoint
```
2. 
```swift
var startPoint: CGPoint { get set }
```

## endPoint

The end point of the line segment.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) CGPoint endPoint
```
2. 
```swift
var endPoint: CGPoint { get set }
```

## linesConfidenceCoefficients

The confidence coefficients for lines. There are 4 coefficients in this set:  

1. linesConfidenceCoefficients\[0\] is average positive amplitude;
2. linesConfidenceCoefficients\[1\] is max positive amplitude;
3. linesConfidenceCoefficients\[2\] is average negative amplitude;
4. linesConfidenceCoefficients\[3\] is max negative amplitude.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSData* linesConfidenceCoefficients
```
2. 
```swift
var linesConfidenceCoefficients: Data? { get set }
```
