---
layout: default-layout
title: Multi-Frame Cross Filter - Dynamsoft Barcode Reader Android
description: Learn how to use the multi-frame cross filter in Dynamsoft Barcode Reader Android.
keywords: filter, Android, multi-frame cross filter
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

- Frame Window: The number of frames used for cross verification. The default is 5.
- Min Consistent Frames: The number of consistent frames required to pass cross verification. The default is 2.

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

### Set Duplicate Forget Time

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
