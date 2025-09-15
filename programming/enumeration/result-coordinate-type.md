---
layout: default-layout
title: EnumResultCoordinateType
description: Use this enum data type to set constants for result coordinate type of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumResultCoordinateType, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumResultCoordinateType
permalink: /programming/enumeration/result-coordinate-type.html
ignore: true
---


# EnumResultCoordinateType

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumResultCoordinateType {
    public static final int RCT_PIXEL = 1;
    public static final int RCT_PERCENTAGE = 2;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumResultCoordinateType)
{
    /** Returns the coordinate in pixel value. */
    EnumResultCoordinateTypePixel = 0x01,
    /** Returns the coordinate as a percentage. */
    EnumResultCoordinateTypePercentage = 0x02
};
```
>
```swift
public enum EnumResultCoordinateType : Int{
    /** Returns the coordinate in pixel value. */
    pixel = 0x01
    /** Returns the coordinate as a percentage. */
    percentage = 0x02
}
```
