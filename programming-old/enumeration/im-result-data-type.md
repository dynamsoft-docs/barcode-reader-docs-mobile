---
layout: default-layout
title: EnumIMResultDataType
description: Use this enum data type to set constants for data type result of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumIMResultDataType, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumIMResultDataType
permalink: /programming/enumeration/im-result-data-type.html
---


# EnumIMResultDataType

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumIMResultDataType {
    public static final int IMRDT_IMAGE = 1;
    public static final int IMRDT_CONTOUR = 2;
    public static final int IMRDT_LINESEGMENT = 4;
    public static final int IMRDT_LOCALIZATIONRESULT = 8;
    public static final int IMRDT_REGIONOFINTEREST = 16;
    public static final int IMRDT_QUADRILATERAL = 32;
    public static final int IMRDT_REFERENCE = 64;
}
```
>
```objc
typedef NS_ENUM(NSInteger,EnumIMResultDataType)
{
    /**Specifies the ImageData */
    EnumIMResultDataTypeImage = 0x01,
    /**Specifies the Contour */
    EnumIMResultDataTypeContour = 0x02,
    /**Specifies the LineSegment */
    EnumIMResultDataTypeLineSegment = 0x04,
    /**Specifies the LocalizationResult */
    EnumIMResultDataTypeLocalizationResult = 0x08,
    /**Specifies the RegionOfInterest */
    EnumIMResultDataTypeRegionOfInterest = 0x10,
    /**Specifies the Quadrilateral*/
    EnumIMResultDataTypeQuadrilateral = 0x20,
    /**Specifies the internal data for using cross Dynamsoft product. */
    EnumIMResultDataTypeReference = 0x40
};
```
>
```swift
public enum EnumIMResultDataType : Int{
    /**Specifies the ImageData */
    image = 0x01
    /**Specifies the Contour */
    contour = 0x02
    /**Specifies the LineSegment */
    lineSegment = 0x04
    /**Specifies the LocalizationResult */
    localizationResult = 0x08
    /**Specifies the RegionOfInterest */
    regionOfInterest = 0x10
    /**Specifies the Quadrilateral*/
    quadrilateral = 0x20
    /**Specifies the internal data for using cross Dynamsoft product. */
    reference = 0x40
}
```
