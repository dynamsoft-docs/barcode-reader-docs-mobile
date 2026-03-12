---
layout: default-layout
title: Multi-Frame Cross Filter - Dynamsoft Barcode Reader iOS
description: Learn how to use the multi-frame cross filter in Dynamsoft Barcode Reader iOS.
keywords: filter, iOS, multi-frame cross filter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# How to Use Multi-Frame Cross Filter

> [!Important]
> Multi-frame cross filter features are internally implemented in the `BarcodeScanner` component and are not customizable. This page explains how to use them with Foundational APIs.

Multi-frame cross filter is a collection of result-filtering features designed for camera-based barcode scanning.

| Filter Name | Description |
| ----------- | ----------- |
| Cross Verification | Improves accuracy. |
| Overlapping | Improves read rate for multi-barcode scanning. |
| Deduplication | Removes duplicate results. |

## Cross Verification

Cross verification is one of the most commonly used techniques for improving scanning accuracy.

### How to Enable

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
[filter enableResultCrossVerification:DSCapturedResultItemTypeBarcode isEnabled:true];
[self.cvr addResultFilter:filter];
```
2. 
```swift
let filter = MultiFrameResultCrossFilter()
filter.enableResultCrossVerification(.barcode, isEnabled: true)
cvr.addResultFilter(filter)
```

### Set Criteria

- Frame Window: The number of frames used for cross verification. The default is 5.
- Min Consistent Frames: The number of consistent frames required to pass cross verification. The default is 2.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
DSCrossVerificationCriteria *criteria = [[DSCrossVerificationCriteria alloc] init];
criteria.frameWindow = 5;
criteria.minConsistentFrames = 3;
[filter setResultCrossVerificationCriteria:DSCapturedResultItemTypeBarcode criteria:criteria];
```
2. 
```swift
let filter = MultiFrameResultCrossFilter()
let criteria = CrossVerificationCriteria()
criteria.frameWindow = 5
criteria.minConsistentFrames = 3
filter.setResultCrossVerificationCriteria(.barcode, criteria: criteria)
```

## Overlapping

### How to Enable

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
[filter enableLatestOverlapping:DSCapturedResultItemTypeBarcode isEnabled:true];
[self.cvr addResultFilter:filter];
```
2. 
```swift
let filter = MultiFrameResultCrossFilter()
filter.enableLatestOverlapping(.barcode, isEnabled: true)
cvr.addResultFilter(filter)
```

### Maximum Overlapping Frames

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
[filter setMaxOverlappingFrames:DSCapturedResultItemTypeBarcode frames:10];
```
2. 
```swift
let filter = MultiFrameResultCrossFilter()
filter.setMaxOverlappingFrames(.barcode, frames: 10)
```

## Deduplication

### How to Enable

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
[filter enableResultDeduplication:DSCapturedResultItemTypeBarcode isEnabled:true];
[self.cvr addResultFilter:filter];
```
2. 
```swift
let filter = MultiFrameResultCrossFilter()
filter.enableResultDeduplication(.barcode, isEnabled: true)
cvr.addResultFilter(filter)
```

### Set Duplicate Forget Time

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
[filter setDuplicateForgetTime:DSCapturedResultItemTypeBarcode time:5000];
[filter enableResultDeduplication:DSCapturedResultItemTypeBarcode isEnabled:true];
```
2. 
```swift
let filter = MultiFrameResultCrossFilter()
filter.setDuplicateForgetTime(.barcode, time: 5000)
filter.enableResultDeduplication(.barcode, isEnabled: true)
```
