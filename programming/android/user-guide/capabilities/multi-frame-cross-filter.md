---
layout: default-layout
title: Multi-Frame Cross Filter - Dynamsoft Barcode Reader Android
description: Learn how to use multi-frame cross filter for Dynamsoft Barcode Reader Android.
keywords: filter, Android, multi-frame cross filter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# How to use Multi-Frame Cross Filter

> [!Important]
> Multi-Frame cross filter features are internally implemented in `BarcodeScanner` component and not customizable. This page only introduces how to use them with Foundational APIs.

Multi-Frame Cross Filter is a collection of result-filtering features designed for scanning barcodes from the camera. .

| Filter Name | Description |
| ----------- | ----------- |
| Cross Verification | Improve the accuracy. |
| Overlapping | Improve the read-rate of multiple barcode scanning. |
| Deduplication | Remove the duplicate results. |

## Cross Verification

Cross verification is one of the most commonly used techniques for improving scanning accuracy.

### How to Enable

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
MultiFrameResultCrossFilter filter = new MultiFrameResultCrossFilter();
filter.enableResultCrossVerification(EnumCapturedResultItemType.CRIT_BARCODE, true);
```
2. 
```kotlin
val filter: MultiFrameResultCrossFilter = MultiFrameResultCrossFilter()
filter.enableResultCrossVerification(EnumCapturedResultItemType.CRIT_BARCODE, true)
```

### Set Criteria

- Frame Window: How many frames to check for the cross verification. Default is 5.
- Min Consistent Frames: How many frames need to be consistent to pass the cross verification. Default is 2.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
MultiFrameResultCrossFilter filter = new MultiFrameResultCrossFilter();
CrossVerificationCriteria criteria = new CrossVerificationCriteria();
criteria.setFrameWindow(5);
criteria.setMinConsistentFrames(3);
filter.setResultCrossVerificationCriteria(EnumCapturedResultItemType.CRIT_BARCODE, criteria);
```
2. 
```kotlin
val filter: MultiFrameResultCrossFilter = MultiFrameResultCrossFilter()
val criteria = CrossVerificationCriteria()
criteria.setFrameWindow(5)
criteria.setMinConsistentFrames(3)
filter.setResultCrossVerificationCriteria(EnumCapturedResultItemType.CRIT_BARCODE, criteria)
```

## Overlapping

### How to Enable

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
MultiFrameResultCrossFilter filter = new MultiFrameResultCrossFilter();
filter.enableLatestOverlapping(EnumCapturedResultItemType.CRIT_BARCODE, true);
```
2. 
```kotlin
val filter: MultiFrameResultCrossFilter = MultiFrameResultCrossFilter()
filter.enableLatestOverlapping(EnumCapturedResultItemType.CRIT_BARCODE, true)
```

### Maximum Overlapping Frames

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
MultiFrameResultCrossFilter filter = new MultiFrameResultCrossFilter();
filter.setMaxOverlappingFrames(EnumCapturedResultItemType.CRIT_BARCODE, 10);
```
2. 
```kotlin
val filter: MultiFrameResultCrossFilter = MultiFrameResultCrossFilter()
filter.setMaxOverlappingFrames(EnumCapturedResultItemType.CRIT_BARCODE, 10)
```

## Deduplication

### How to Enable

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
MultiFrameResultCrossFilter filter = new MultiFrameResultCrossFilter();
filter.enableResultDeduplication(EnumCapturedResultItemType.CRIT_BARCODE, true);
```
2. 
```kotlin
val filter: MultiFrameResultCrossFilter = MultiFrameResultCrossFilter()
filter.enableResultDeduplication(EnumCapturedResultItemType.CRIT_BARCODE, true)
```

### Set Duplicate ForgetTime

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
MultiFrameResultCrossFilter filter = new MultiFrameResultCrossFilter();
filter.setDuplicateForgetTime(EnumCapturedResultItemType.CRIT_BARCODE, 5000);
filter.enableResultDeduplication(EnumCapturedResultItemType.CRIT_BARCODE, true);
```
2. 
```kotlin
val filter: MultiFrameResultCrossFilter = MultiFrameResultCrossFilter()
filter.setDuplicateForgetTime(EnumCapturedResultItemType.CRIT_BARCODE, 5000)
filter.enableResultDeduplication(EnumCapturedResultItemType.CRIT_BARCODE, true)
```
