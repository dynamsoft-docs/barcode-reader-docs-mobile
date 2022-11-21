---
layout: default-layout
title: Dynamsoft Barcode Reader Objective-C & Swift API Reference - iLocalizationResult Class
description: This page shows the iLocalizationResult Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iLocalizationResult, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iLocalizationResult.html
---


# Class iLocalizationResult

The `iLocalizationResult` extends the class [`iTextResult`](auxiliary-iTextResult.md) and [`iIntermediateResult`](auxiliary-iIntermediateResult.md). It stores the barcode localization data.

```objc
@interface iLocalizationResult
```  

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`terminatePhase`](#terminatephase) | [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift) | The terminate phase of localization result. |
| [`barcodeFormat`](#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](#barcodeformat_2 ) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](#barcodeformatstring) | *NSString \** | Barcode type as string. |
| [`resultPoints`](#resultpoints) | *NSArray \** | The vertices coordinates information of the barcode region. |
| [`angle`](#angle) | *NSInteger* | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](#pagenumber) | *NSInteger* | The page number the barcode located in. The index is 0-based. |
| [`regionName`](#regionname) | *NSString \** | The region name the barcode located in. |
| [`documentName`](#documentname)| *NSString \** | The document name. |
| [`resultCoordinateType`](#resultcoordinatetype) | [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift) | The coordinate type. |
| [`accompanyingTextBytes`](#accompanyingtextbytes) | *NSData \** | The accompanying text content in a byte array. |
| [`confidence`](#confidence) | *NSInteger* | The confidence of the localization result. |
| [`transformationMatrix`](#transformationmatrix) | *CGAffineTransform* | A transformation matrix that can transform the coordinates of the `resultPoints`. The transformationMatrix is calculated from the orientation information of the image. |

## terminatePhase

The terminate phase of localization result.

```objc
@property (nonatomic, assign) EnumTerminatePhase terminatePhase
```

## barcodeFormat

Barcode type in BarcodeFormat group 1.

```objc
@property (nonatomic, assign) EnumBarcodeFormat barcodeFormat
```

## barcodeFormat_2

Barcode type in BarcodeFormat group 2.

```objc
@property (nonatomic, assign) EnumBarcodeFormat2 barcodeFormat_2
```

## barcodeFormatString

Barcode type as string.

```objc
@property (nonatomic, nullable) NSString* barcodeFormatString
```

## resultPoints

The resultPoints are Four CGPoints that localize the result area.

```objc
@property (nonatomic, nullable) NSArray* resultPoints
```

## angle

The angle of a barcode. Values range is from 0 to 360.

```objc
@property (nonatomic, assign) NSInteger angle
```

## moduleSize

The barcode module size (the minimum bar width in pixel).

```objc
@property (nonatomic, assign) NSInteger moduleSize
```

## pageNumber

The page number the barcode located in. The index is 0-based.

```objc
@property (nonatomic, assign) NSInteger pageNumber
```

## regionName

The region name the barcode located in.

```objc
@property (nonatomic, nullable) NSString* regionName
```

## documentName

The document name.

```objc
@property (nonatomic, nullable) NSString* documentName
```

## resultCoordinateType

The coordinate type.

```objc
@property (nonatomic, assign) EnumResultCoordinateType resultCoordinateType
```

## accompanyingTextBytes

The accompanying text content in a byte array.

```objc
@property (nonatomic, nullable) NSData* accompanyingTextBytes
```

## confidence

The confidence of the localization result.

```objc
@property (nonatomic, assign) NSInteger confidence
```

## transformationMatrix

A transformation matrix that can transform the coordinates of the `resultPoints`. The `transformationMatrix` is calculated from the orientation information of the image.

The images that captured by mobile cameras are always 90 degree counterclockwise rotated from what you see. The coordinates of `resultPoints` are based on the **image coordinate system**. You can use the `transformationMatrix` to rotate the resultPoints from the **image coordinate system** to the **real coordinate system**.

```objc
@property (nonatomic) CGAffineTransform transformationMatrix;
```
