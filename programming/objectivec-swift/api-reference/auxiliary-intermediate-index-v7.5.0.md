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

## [iIntermediateResult](auxiliary-iIntermediateResult.html)

`iIntermediateResult` is the class that stores the intermediate result data.

```objc
@interface iIntermediateResult 
```  

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`resultsCount`](auxiliary-iIntermediateResult.html#resultscount) | *NSInteger* | The total result count. |
| [`results`](auxiliary-iIntermediateResult.html#results) | *NSObject\** | One of the following types: Array of [`iContour`](auxiliary-iContour.html), Array of [`iImageData`](auxiliary-iImageData.html), Array of [`iLineSegment`](auxiliary-iLineSegment.html), Array of [`iLocalizationResult`](auxiliary-iLocalizationResult.html), Array of [`iRegionOfInterest`](auxiliary-iRegionOfInterest.html). |
| [`dataType`](auxiliary-iIntermediateResult.html#datatype) | [`EnumIMResultDataType`]({{ site.mobile_enum }}im-result-data-type.html?lang=objc,swift) | The data type of the intermediate result. |
| [`resultType`](auxiliary-iIntermediateResult.html#resulttype) | [`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=objc,swift) | Intermediate result type. |
| [`barcodeComplementMode`](auxiliary-iIntermediateResult.html#barcodecomplementmode) | [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) | The [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`bcmIndex`](auxiliary-iIntermediateResult.html#bcmindex) | *NSInteger* | The array index of current used [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) in the [`barcodeComplementModes`](auxiliary-iFurtherModes.html#barcodecomplementmodes) setting. |
| [`deformationResistingMode`](auxiliary-iIntermediateResult.html#deformationresistingmode) | [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) | The [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`drmIndex`](auxiliary-iIntermediateResult.html#drmindex) | *NSInteger* | The array index of current used [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) in the [`deformationResistingModes`](auxiliary-iFurtherModes.html#deformationresistingmodes) setting. |
| [`dpmCodeReadingMode`](auxiliary-iIntermediateResult.html#dpmcodereadingmode) | [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) | The [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`dpmcrmIndex`](auxiliary-iIntermediateResult.html#dpmcrmindex) | *NSInteger* | The array index of current used [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) in the [`dpmCodeReadingModes`](auxiliary-iFurtherModes.html#dpmcodereadingmodes) setting. |
| [`transformationMatrix`](auxiliary-iIntermediateResult.html#transformationMatrix) | *NSArray \** | The rotation matrix. |
| [`textFilterMode`](auxiliary-iIntermediateResult.html#textfiltermode) | [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) | The [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`tfmIndex`](auxiliary-iIntermediateResult.html#tfmindex) | *NSInteger* | The array index of current used [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) in the [`textFilterModes`](auxiliary-iFurtherModes.html#textfiltermodes) setting. |
| [`localizationMode`](auxiliary-iIntermediateResult.html#localizationmode) | [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) | The [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`lmIndex`](auxiliary-iIntermediateResult.html#lmindex) | *NSInteger* | The array index of current used [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) in the [`localizationModes`](auxiliary-iPublicRuntimeSettings.html#localizationmodes) setting. |
| [`binarizationMode`](auxiliary-iIntermediateResult.html#binarizationmode) | [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) | The [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`bmIndex`](auxiliary-iIntermediateResult.html#bmindex) | *NSInteger* | The array index of current used [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) in the [`binarizationModes`](auxiliary-iPublicRuntimeSettings.html#binarizationmodes) setting. |
| [`imagePreprocessingMode`](auxiliary-iIntermediateResult.html#imagepreprocessingmode) | [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) | The [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`ipmIndex`](auxiliary-iIntermediateResult.html#ipmindex) | *NSInteger* | The array index of current used [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) in [`imagePreprocessingModes`](auxiliary-iFurtherModes.html#imagepreprocessingmodes) setting. |
| [`roiId`](auxiliary-iIntermediateResult.html#roiid) | *NSInteger* | The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image. |
| [`regionPredetectionMode`](auxiliary-iIntermediateResult.html#regionpredetectionmode) | [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) | The [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`rpmIndex`](auxiliary-iIntermediateResult.html#rpmindex) | *NSInteger* | The array index of current used [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) in the [`regionPredetectionModes`](auxiliary-iFurtherModes.html#regionpredetectionmodes) setting. |
| [`grayscaleTransformationMode`](auxiliary-iIntermediateResult.html#grayscaletransformationmode) | [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) | The [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`gtmIndex`](auxiliary-iIntermediateResult.html#gtmindex) | *NSInteger* | The array index of current used [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) in the [`grayscaleTransformationModes`](auxiliary-iFurtherModes.html#grayscaletransformationmodes) setting. |
| [`colourConversionMode`](auxiliary-iIntermediateResult.html#colourconversionmode) | [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) | The [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`cicmIndex`](auxiliary-iIntermediateResult.html#cicmindex) | *NSInteger* | The array index of current used [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) in the [`colourConversionModes`](auxiliary-iFurtherModes.html#colourconversionmodes) setting. |
| [`colourClusteringMode`](auxiliary-iIntermediateResult.html#colourclusteringmode) | [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) | The [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`ccmIndex`](auxiliary-iIntermediateResult.html#ccmindex) | *NSInteger* | The array index of current used [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) in the [`colourClusteringModes`](auxiliary-iFurtherModes.html#colourclusteringmodes) setting. |
| [`scaleDownRatio`](auxiliary-iIntermediateResult.html#scaledownratio) | *NSInteger* | The scale down ratio. |
| [`frameId`](auxiliary-iIntermediateResult.html#frameid) | *NSInteger* | The ID of the operated frame. |

## [iContour](auxiliary-iContour.html)

`contour` is one of the [`results`](#intermediateresult) type in `IntermediateResult`.

```objc
@interface iContour
```  

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`pointsCount`](auxiliary-iContour.html#pointscount) |  *NSInteger* | The total points count of the contour. |
| [`points`](auxiliary-iContour.html#points) | *NSArray* \* | The points array of the points that surround the barcode area.. |

## [iImageData](auxiliary-iImageData.html)

`ImageData` is one of the [`results`](#intermediateresult) type in `IntermediateResult`.

```objc
@interface iImageData
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`bytes`](auxiliary-iImageData.html#bytes) | *unsigned char\** | The image data content in a byte array. |
| [`bytesLength`](auxiliary-iImageData.html#byteslength) | *NSInteger* | The length of the image data byte array. |
| [`width`](auxiliary-iImageData.html#width) | *NSInteger* | The width of the image in pixels. |
| [`height`](auxiliary-iImageData.html#height) | *NSInteger* | The height of the image in pixels. |
| [`stride`](auxiliary-iImageData.html#stride) | *NSInteger* | The stride (or scan width) of the image. |
| [`format`](auxiliary-iImageData.html#format) | [`EnumImagePixelFormat`]({{ site.mobile_enum }}image-pixel-format.html?lang=objc,swift) | The image pixel format used in the image byte array. |

## [iLineSegment](auxiliary-iLineSegment.html)

`LineSegment` is one of the [`results`](auxiliary-iIntermediateResult.html#results) type in `IntermediateResult`.

```objc
@interface iLineSegment
```  

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`startPoint`](auxiliary-iLineSegment.html#startpoint) | `CGPoint` | The start point of the line segment. |
| [`endPoint`](auxiliary-iLineSegment.html#endpoint) | `CGPoint` | The end point of the line segment. |
| [`linesConfidenceCoefficients`](auxiliary-iLineSegment.html#linesconfidencecoefficients) | *NSData \** | *byte\[\]* | The confidence coefficients for lines. |

## [iRegionOfInterest](auxiliary-iRegionOfInterest.html)

`RegionOfInterest` is one of the [`results`](auxiliary-iIntermediateResult.html#results) type in `IntermediateResult`.

```objc
@interface iRegionOfInterest
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`roiId`](auxiliary-iRegionOfInterest.html#roiid) | *NSInteger* | The ID generated by the SDK. |
| [`point`](auxiliary-iRegionOfInterest.html#point) | `CGPoint` | The left top point of the region. |
| [`width`](auxiliary-iRegionOfInterest.html#width) | *NSInteger* | The width of the region. |
| [`height`](auxiliary-iRegionOfInterest.html#height) | *NSInteger* | The height of the region. |

## iLocalizationResult

View more in [TextResult >> LocalizationResult](auxiliary-iLocalizationResult.html)

`LocalizationResult` can be the extension of the class [`IntermediateResult`](auxiliary-iIntermediateResult.html). It stores the localization result information.

```objc
@interface iLocalizationResult
```

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`terminatePhase`](auxiliary-iLocalizationResult.html#terminatephase) | [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift) | The terminate phase of localization result. |
| [`barcodeFormat`](auxiliary-iLocalizationResult.html#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](auxiliary-iLocalizationResult.html#barcodeformatstring) | *NSString \** | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](auxiliary-iLocalizationResult.html#barcodeformat_2 ) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](auxiliary-iLocalizationResult.html#barcodeformatstring_2) | *NSString \** | Barcode type in BarcodeFormat group 2 as string. |
| [`resultPoints`](auxiliary-iLocalizationResult.html#resultpoints) | *NSArray \** | The vertices coordinates information of the barcode region. |
| [`angle`](auxiliary-iLocalizationResult.html#angle) | *NSInteger* | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](auxiliary-iLocalizationResult.html#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](auxiliary-iLocalizationResult.html#pagenumber) | *NSInteger* | The page number the barcode located in. The index is 0-based. |
| [`regionName`](auxiliary-iLocalizationResult.html#regionname) | *NSString \** | The region name the barcode located in. |
| [`documentName`](auxiliary-iLocalizationResult.html#documentname)| *NSString \** | The document name. |
| [`resultCoordinateType`](auxiliary-iLocalizationResult.html#resultcoordinatetype) | [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift) | The coordinate type. |
| [`accompanyingTextBytes`](auxiliary-iLocalizationResult.html#accompanyingtextbytes) | *NSData \** | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](auxiliary-iLocalizationResult.html#accompanyingtextbyteslength) | *NSInteger* | The length of the accompanying text byte array. |
| [`confidence`](auxiliary-iLocalizationResult.html#confidence) | *NSInteger* | The confidence of the localization result. |
