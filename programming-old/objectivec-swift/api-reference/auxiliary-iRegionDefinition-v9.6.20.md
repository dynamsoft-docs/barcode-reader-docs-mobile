---
layout: default-layout
title: iRegionDefinition Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iRegionDefinition Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iRegionDefinition, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iRegionDefinition-v9.6.20.html
---

# Class iRegionDefinition

Stores the region information.  

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
| [`regionTop`](#regiontop) | The top-most coordinate or percentage of the region. |
| [`regionLeft`](#regionleft) | The Left-most coordinate or percentage of the region. |
| [`regionRight`](#regionright) | The Right-most coordinate or percentage of the region. |
| [`regionBottom`](#regionbottom) | The Bottom-most coordinate or percentage of the region. |
| [`regionMeasuredByPercentage`](#regionmeasuredbypercentage) | Sets whether or not to use percentage to measure the region size. |

## regionTop

The top-most coordinate or percentage of the region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger regionTop;
```
2. 
```swift
var regionTop: Int { get set }
```

**Value Range**

regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
regionMeasuredByPercentage = 1: [0, 100]  

**Default Value**

0

## regionLeft

The left-most coordinate or percentage of the region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger regionLeft;
```
2. 
```swift
var regionLeft: Int { get set }
```

**Value Range**

regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
regionMeasuredByPercentage = 1: [0, 100]  

**Default Value**

0

## regionRight

The right-most coordinate or percentage of the region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger regionRight;
```
2. 
```swift
var regionRight: Int { get set }
```

**Value Range**

regionMeasuredByPercentage = 0: [0, 0x7fffffff]
regionMeasuredByPercentage = 1: [0, 100]

**Default Value**

0

## regionBottom

The bottom-most coordinate or percentage of the region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger regionBottom;
```
2. 
```swift
var regionBottom: Int { get set }
```

**Value Range**

regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
regionMeasuredByPercentage = 1: [0, 100]  

**Default Value**

0

## regionMeasuredByPercentage

Sets whether or not to use percentage to measure the region size.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger regionMeasuredByPercentage;
```
2. 
```swift
var regionMeasuredByPercentage: Int { get set }
```

**Value Range**

[0, 1]

**Default Value**

0

**Remarks**

When it's set to 1, the values of Top, Left, Right, Bottom indicate percentage (from 0 to 100); Otherwise, they indicate coordinates. 0: not by percentage 1: by percentage.
