---
layout: default-layout
title: EnumGrayscaleTransformationMode
description: Use this enum data type to set constants for grayscale transformation mode of barcodes in your Dynamsoft Barcode Reader for JavaScript.
keywords: EnumGrayscaleTransformationMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumGrayscaleTransformationMode
permalink: /programming/enumeration/grayscale-transformation-mode.html
---


# EnumGrayscaleTransformationMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumGrayscaleTransformationMode {
    public static final int GTM_INVERTED = 1;
    public static final int GTM_ORIGINAL = 2;
    public static final int GTM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumGrayscaleTransformationMode)
{
    /** Transforms to the inverted grayscale for further reference. This value is recommended for light on dark images. */
    EnumGrayscaleTransformationModeInverted = 0x01,
    /** Keeps the original grayscale for further reference. This value is recommended for dark on light images. */
    EnumGrayscaleTransformationModeOriginal = 0x02,
    /** Skips grayscale transformation. */
    EnumGrayscaleTransformationModeSkip = 0x00
};
```
>
```swift
public enum EnumGrayscaleTransformationMode : Int{
    /** Transforms to the inverted grayscale for further reference. This value is recommended for light on dark images. */
    inverted = 0x01
    /** Keeps the original grayscale for further reference. This value is recommended for dark on light images. */
    original = 0x02
    /** Skips grayscale transformation. */
    skip = 0x00
}
```
