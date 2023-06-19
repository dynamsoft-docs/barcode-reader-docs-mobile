---
layout: default-layout
title: iIntermediateResult index - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iIntermediateResult index of Dynamsoft Barcode Reader for iOS SDK.
keywords: IntermediateResult, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: False
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-intermediate-index-v7.5.0.html
---

# Intermediate Result Classes

## [iIntermediateResult](auxiliary-iIntermediateResult.md)

`iIntermediateResult` is the class that stores the intermediate result data.

```objc
@interface iIntermediateResult 
```  

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`resultsCount`](auxiliary-iIntermediateResult.md#resultscount) | *NSInteger* | The total result count. |
| [`results`](auxiliary-iIntermediateResult.md#results) | *NSObject\** | One of the following types: Array of [`iContour`](auxiliary-iContour.md), Array of [`iImageData`](auxiliary-iImageData.md), Array of [`iLineSegment`](auxiliary-iLineSegment.md), Array of [`iLocalizationResult`](auxiliary-iLocalizationResult.md), Array of [`iRegionOfInterest`](auxiliary-iRegionOfInterest.md). |
| [`dataType`](auxiliary-iIntermediateResult.md#datatype) | [`EnumIMResultDataType`]({{ site.mobile_enum }}im-result-data-type.html?lang=objc,swift) | The data type of the intermediate result. |
| [`resultType`](auxiliary-iIntermediateResult.md#resulttype) | [`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=objc,swift) | Intermediate result type. |
| [`barcodeComplementMode`](auxiliary-iIntermediateResult.md#barcodecomplementmode) | [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) | The [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`bcmIndex`](auxiliary-iIntermediateResult.md#bcmindex) | *NSInteger* | The array index of current used [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) in the [`barcodeComplementModes`](auxiliary-iFurtherModes.md#barcodecomplementmodes) setting. |
| [`deformationResistingMode`](auxiliary-iIntermediateResult.md#deformationresistingmode) | [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) | The [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`drmIndex`](auxiliary-iIntermediateResult.md#drmindex) | *NSInteger* | The array index of current used [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) in the [`deformationResistingModes`](auxiliary-iFurtherModes.md#deformationresistingmodes) setting. |
| [`dpmCodeReadingMode`](auxiliary-iIntermediateResult.md#dpmcodereadingmode) | [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) | The [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`dpmcrmIndex`](auxiliary-iIntermediateResult.md#dpmcrmindex) | *NSInteger* | The array index of current used [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) in the [`dpmCodeReadingModes`](auxiliary-iFurtherModes.md#dpmcodereadingmodes) setting. |
| [`transformationMatrix`](auxiliary-iIntermediateResult.md#transformationMatrix) | *NSArray \** | The rotation matrix. |
| [`textFilterMode`](auxiliary-iIntermediateResult.md#textfiltermode) | [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) | The [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`tfmIndex`](auxiliary-iIntermediateResult.md#tfmindex) | *NSInteger* | The array index of current used [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) in the [`textFilterModes`](auxiliary-iFurtherModes.md#textfiltermodes) setting. |
| [`localizationMode`](auxiliary-iIntermediateResult.md#localizationmode) | [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) | The [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`lmIndex`](auxiliary-iIntermediateResult.md#lmindex) | *NSInteger* | The array index of current used [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) in the [`localizationModes`](auxiliary-iPublicRuntimeSettings.md#localizationmodes) setting. |
| [`binarizationMode`](auxiliary-iIntermediateResult.md#binarizationmode) | [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) | The [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`bmIndex`](auxiliary-iIntermediateResult.md#bmindex) | *NSInteger* | The array index of current used [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) in the [`binarizationModes`](auxiliary-iPublicRuntimeSettings.md#binarizationmodes) setting. |
| [`imagePreprocessingMode`](auxiliary-iIntermediateResult.md#imagepreprocessingmode) | [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) | The [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`ipmIndex`](auxiliary-iIntermediateResult.md#ipmindex) | *NSInteger* | The array index of current used [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) in [`imagePreprocessingModes`](auxiliary-iFurtherModes.md#imagepreprocessingmodes) setting. |
| [`roiId`](auxiliary-iIntermediateResult.md#roiid) | *NSInteger* | The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image. |
| [`regionPredetectionMode`](auxiliary-iIntermediateResult.md#regionpredetectionmode) | [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) | The [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`rpmIndex`](auxiliary-iIntermediateResult.md#rpmindex) | *NSInteger* | The array index of current used [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) in the [`regionPredetectionModes`](auxiliary-iFurtherModes.md#regionpredetectionmodes) setting. |
| [`grayscaleTransformationMode`](auxiliary-iIntermediateResult.md#grayscaletransformationmode) | [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) | The [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`gtmIndex`](auxiliary-iIntermediateResult.md#gtmindex) | *NSInteger* | The array index of current used [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) in the [`grayscaleTransformationModes`](auxiliary-iFurtherModes.md#grayscaletransformationmodes) setting. |
| [`colourConversionMode`](auxiliary-iIntermediateResult.md#colourconversionmode) | [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) | The [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`cicmIndex`](auxiliary-iIntermediateResult.md#cicmindex) | *NSInteger* | The array index of current used [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) in the [`colourConversionModes`](auxiliary-iFurtherModes.md#colourconversionmodes) setting. |
| [`colourClusteringMode`](auxiliary-iIntermediateResult.md#colourclusteringmode) | [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) | The [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`ccmIndex`](auxiliary-iIntermediateResult.md#ccmindex) | *NSInteger* | The array index of current used [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) in the [`colourClusteringModes`](auxiliary-iFurtherModes.md#colourclusteringmodes) setting. |
| [`scaleDownRatio`](auxiliary-iIntermediateResult.md#scaledownratio) | *NSInteger* | The scale down ratio. |
| [`frameId`](auxiliary-iIntermediateResult.md#frameid) | *NSInteger* | The ID of the operated frame. |

## [iContour](auxiliary-iContour.md)

`contour` is one of the [`results`](#intermediateresult) type in `IntermediateResult`.

```objc
@interface iContour
```  

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`pointsCount`](auxiliary-iContour.md#pointscount) |  *NSInteger* | The total points count of the contour. |
| [`points`](auxiliary-iContour.md#points) | *NSArray* \* | The points array of the points that surround the barcode area.. |

## [iImageData](auxiliary-iImageData.md)

`ImageData` is one of the [`results`](#intermediateresult) type in `IntermediateResult`.

```objc
@interface iImageData
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`bytes`](auxiliary-iImageData.md#bytes) | *unsigned char\** | The image data content in a byte array. |
| [`bytesLength`](auxiliary-iImageData.md#byteslength) | *NSInteger* | The length of the image data byte array. |
| [`width`](auxiliary-iImageData.md#width) | *NSInteger* | The width of the image in pixels. |
| [`height`](auxiliary-iImageData.md#height) | *NSInteger* | The height of the image in pixels. |
| [`stride`](auxiliary-iImageData.md#stride) | *NSInteger* | The stride (or scan width) of the image. |
| [`format`](auxiliary-iImageData.md#format) | [`EnumImagePixelFormat`]({{ site.mobile_enum }}image-pixel-format.html?lang=objc,swift) | The image pixel format used in the image byte array. |

## [iLineSegment](auxiliary-iLineSegment.md)

`LineSegment` is one of the [`results`](auxiliary-iIntermediateResult.md#results) type in `IntermediateResult`.

```objc
@interface iLineSegment
```  

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`startPoint`](auxiliary-iLineSegment.md#startpoint) | `CGPoint` | The start point of the line segment. |
| [`endPoint`](auxiliary-iLineSegment.md#endpoint) | `CGPoint` | The end point of the line segment. |
| [`linesConfidenceCoefficients`](auxiliary-iLineSegment.md#linesconfidencecoefficients) | *NSData \** | *byte\[\]* | The confidence coefficients for lines. |

## [iRegionOfInterest](auxiliary-iRegionOfInterest.md)

`RegionOfInterest` is one of the [`results`](auxiliary-iIntermediateResult.md#results) type in `IntermediateResult`.

```objc
@interface iRegionOfInterest
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`roiId`](auxiliary-iRegionOfInterest.md#roiid) | *NSInteger* | The ID generated by the SDK. |
| [`point`](auxiliary-iRegionOfInterest.md#point) | `CGPoint` | The left top point of the region. |
| [`width`](auxiliary-iRegionOfInterest.md#width) | *NSInteger* | The width of the region. |
| [`height`](auxiliary-iRegionOfInterest.md#height) | *NSInteger* | The height of the region. |

## iLocalizationResult

View more in [TextResult >> LocalizationResult](auxiliary-iLocalizationResult.md)

`LocalizationResult` can be the extension of the class [`IntermediateResult`](auxiliary-iIntermediateResult.md). It stores the localization result information.

```objc
@interface iLocalizationResult
```

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`terminatePhase`](auxiliary-iLocalizationResult.md#terminatephase) | [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift) | The terminate phase of localization result. |
| [`barcodeFormat`](auxiliary-iLocalizationResult.md#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](auxiliary-iLocalizationResult.md#barcodeformatstring) | *NSString \** | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](auxiliary-iLocalizationResult.md#barcodeformat_2 ) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](auxiliary-iLocalizationResult.md#barcodeformatstring_2) | *NSString \** | Barcode type in BarcodeFormat group 2 as string. |
| [`resultPoints`](auxiliary-iLocalizationResult.md#resultpoints) | *NSArray \** | The vertices coordinates information of the barcode region. |
| [`angle`](auxiliary-iLocalizationResult.md#angle) | *NSInteger* | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](auxiliary-iLocalizationResult.md#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](auxiliary-iLocalizationResult.md#pagenumber) | *NSInteger* | The page number the barcode located in. The index is 0-based. |
| [`regionName`](auxiliary-iLocalizationResult.md#regionname) | *NSString \** | The region name the barcode located in. |
| [`documentName`](auxiliary-iLocalizationResult.md#documentname)| *NSString \** | The document name. |
| [`resultCoordinateType`](auxiliary-iLocalizationResult.md#resultcoordinatetype) | [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift) | The coordinate type. |
| [`accompanyingTextBytes`](auxiliary-iLocalizationResult.md#accompanyingtextbytes) | *NSData \** | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](auxiliary-iLocalizationResult.md#accompanyingtextbyteslength) | *NSInteger* | The length of the accompanying text byte array. |
| [`confidence`](auxiliary-iLocalizationResult.md#confidence) | *NSInteger* | The confidence of the localization result. |
