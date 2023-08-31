---
layout: default-layout
title: EnumIntermediateResultType
description: Use this enum data type to set constants for intermediate result type of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumIntermediateResultType, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumIntermediateResultType
permalink: /programming/enumeration/intermediate-result-type.html
---


# EnumIntermediateResultType

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumIntermediateResultType {
    public static final int IRT_NO_RESULT = 0;
    public static final int IRT_ORIGINAL_IMAGE = 1;
    public static final int IRT_COLOUR_CLUSTERED_IMAGE = 2;
    public static final int IRT_COLOUR_CONVERTED_GRAYSCALE_IMAGE = 4;
    public static final int IRT_TRANSFORMED_GRAYSCALE_IMAGE = 8;
    public static final int IRT_PREDETECTED_REGION = 16;
    public static final int IRT_PREPROCESSED_IMAGE = 32;
    public static final int IRT_BINARIZED_IMAGE = 64;
    public static final int IRT_TEXT_ZONE = 128;
    public static final int IRT_CONTOUR = 256;
    public static final int IRT_LINE_SEGMENT = 512;
    public static final int IRT_FORM = 1024;
    public static final int IRT_SEGMENTATION_BLOCK = 2048;
    public static final int IRT_TYPED_BARCODE_ZONE = 4096;
    public static final int IRT_PREDETECTED_QUADRILATERAL = 8192;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumIntermediateResultType)
{
    /** No intermediate result */
    EnumIntermediateResultTypeNoResult = 0x00,
    /** Original image */
    EnumIntermediateResultTypeOriginalImage = 0x01,
    /** Colour clustered image. Not supported yet. */
    EnumIntermediateResultTypeColourClusteredImage = 0x02,
    /** Colour converted grayscale image */
    EnumIntermediateResultTypeColourConvertedGrayScaleImage = 0x04,
    /** Transformed grayscale image */
    EnumIntermediateResultTypeTransformedGrayScaleImage = 0x08,
    /** Predetected region */
    EnumIntermediateResultTypePredetectedRegion = 0x10,
    /** Preprocessed image */
    EnumIntermediateResultTypePreprocessedImage = 0x20,
    /** Binarized image */
    EnumIntermediateResultTypeBinarizedImage = 0x40,
    /** Text zone */
    EnumIntermediateResultTypeTextZone = 0x80,
    /** Contour */
    EnumIntermediateResultTypeContour = 0x100,
    /** Line segment */
    EnumIntermediateResultTypeLineSegment = 0x200,
    /** Form. Not supported yet. */
    EnumIntermediateResultTypeForm = 0x400,
    /** Segmentation block. Not supported yet. */
    EnumIntermediateResultTypeSegmentationBlock = 0x800,
    /** Typed barcode zone */
    EnumIntermediateResultTypeTypedBarcodeZone = 0x1000,
    /** Predetected quadrilateral  */
    EnumIntermediateResultTypePredetectedQuadrilateral = 0x2000
};
```
>
```swift
public enum EnumIntermediateResultType : Int{
    /** No intermediate result */
    noResult = 0x00
    /** Original image */
    originalImage = 0x01
    /** Colour clustered image. Not supported yet. */
    colourClusteredImage = 0x02
    /** Colour converted grayscale image */
    colourConvertedGrayScaleImage = 0x04
    /** Transformed grayscale image */
    transformedGrayScaleImage = 0x08
    /** Predetected region */
    predetectedRegion = 0x10
    /** Preprocessed image */
    preprocessedImage = 0x20
    /** Binarized image */
    binarizedImage = 0x40
    /** Text zone */
    textZone = 0x80
    /** Contour */
    contour = 0x100
    /** Line segment */
    lineSegment = 0x200
    /** Form. Not supported yet. */
    form = 0x400
    /** Segmentation block. Not supported yet. */
    segmentationBlock = 0x800
    /** Typed barcode zone */
    typedBarcodeZone = 0x1000
    /** Predetected quadrilateral  */
    predetectedQuadrilateral = 0x2000
}
```
