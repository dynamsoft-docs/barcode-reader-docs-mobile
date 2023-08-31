---
layout: default-layout
title: iIntermediateResult index - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iIntermediateResult index of Dynamsoft Barcode Reader for iOS SDK.
keywords: IntermediateResult, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: False
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-intermediate-index-v9.6.20.html
---

# Intermediate Result Classes

## [iIntermediateResult](auxiliary-iIntermediateResult.md)

`iIntermediateResult` is the class that stores the intermediate result data.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iIntermediateResult : NSObject
```  
2. 
```swift
class iIntermediateResult : NSObject
```

| Attribute | Description |
|---------- | ----------- |
| [`resultsCount`](auxiliary-iIntermediateResult.md#resultscount) | The total result count. |
| [`results`](auxiliary-iIntermediateResult.md#results) | One of the following types: Array of [`iContour`](auxiliary-iContour.md), Array of [`iImageData`](auxiliary-iImageData.md), Array of [`iLineSegment`](auxiliary-iLineSegment.md), Array of [`iLocalizationResult`](auxiliary-iLocalizationResult.md), Array of [`iRegionOfInterest`](auxiliary-iRegionOfInterest.md). |
| [`dataType`](auxiliary-iIntermediateResult.md#datatype) | The data type of the intermediate result. |
| [`resultType`](auxiliary-iIntermediateResult.md#resulttype) | Intermediate result type. |
| [`barcodeComplementMode`](auxiliary-iIntermediateResult.md#barcodecomplementmode) | The [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`bcmIndex`](auxiliary-iIntermediateResult.md#bcmindex) | The array index of current used [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) in the [`barcodeComplementModes`](auxiliary-iFurtherModes.md#barcodecomplementmodes) setting. |
| [`deformationResistingMode`](auxiliary-iIntermediateResult.md#deformationresistingmode) | The [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`drmIndex`](auxiliary-iIntermediateResult.md#drmindex) | The array index of current used [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) in the [`deformationResistingModes`](auxiliary-iFurtherModes.md#deformationresistingmodes) setting. |
| [`dpmCodeReadingMode`](auxiliary-iIntermediateResult.md#dpmcodereadingmode) | The [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`dpmcrmIndex`](auxiliary-iIntermediateResult.md#dpmcrmindex) | The array index of current used [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) in the [`dpmCodeReadingModes`](auxiliary-iFurtherModes.md#dpmcodereadingmodes) setting. |
| [`transformationMatrix`](auxiliary-iIntermediateResult.md#transformationMatrix) | The rotation matrix. |
| [`textFilterMode`](auxiliary-iIntermediateResult.md#textfiltermode) | The [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`tfmIndex`](auxiliary-iIntermediateResult.md#tfmindex) | The array index of current used [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) in the [`textFilterModes`](auxiliary-iFurtherModes.md#textfiltermodes) setting. |
| [`localizationMode`](auxiliary-iIntermediateResult.md#localizationmode) | The [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`lmIndex`](auxiliary-iIntermediateResult.md#lmindex) | The array index of current used [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) in the [`localizationModes`](auxiliary-iPublicRuntimeSettings.md#localizationmodes) setting. |
| [`binarizationMode`](auxiliary-iIntermediateResult.md#binarizationmode) | The [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`bmIndex`](auxiliary-iIntermediateResult.md#bmindex) | The array index of current used [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) in the [`binarizationModes`](auxiliary-iPublicRuntimeSettings.md#binarizationmodes) setting. |
| [`imagePreprocessingMode`](auxiliary-iIntermediateResult.md#imagepreprocessingmode) | The [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`ipmIndex`](auxiliary-iIntermediateResult.md#ipmindex) | The array index of current used [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) in [`imagePreprocessingModes`](auxiliary-iFurtherModes.md#imagepreprocessingmodes) setting. |
| [`roiId`](auxiliary-iIntermediateResult.md#roiid) | The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image. |
| [`regionPredetectionMode`](auxiliary-iIntermediateResult.md#regionpredetectionmode) | The [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`rpmIndex`](auxiliary-iIntermediateResult.md#rpmindex) | The array index of current used [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) in the [`regionPredetectionModes`](auxiliary-iFurtherModes.md#regionpredetectionmodes) setting. |
| [`grayscaleTransformationMode`](auxiliary-iIntermediateResult.md#grayscaletransformationmode) | The [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`gtmIndex`](auxiliary-iIntermediateResult.md#gtmindex) | The array index of current used [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) in the [`grayscaleTransformationModes`](auxiliary-iFurtherModes.md#grayscaletransformationmodes) setting. |
| [`colourConversionMode`](auxiliary-iIntermediateResult.md#colourconversionmode) | The [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`cicmIndex`](auxiliary-iIntermediateResult.md#cicmindex) | The array index of current used [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) in the [`colourConversionModes`](auxiliary-iFurtherModes.md#colourconversionmodes) setting. |
| [`colourClusteringMode`](auxiliary-iIntermediateResult.md#colourclusteringmode) | The [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`ccmIndex`](auxiliary-iIntermediateResult.md#ccmindex) | The array index of current used [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) in the [`colourClusteringModes`](auxiliary-iFurtherModes.md#colourclusteringmodes) setting. |
| [`scaleDownRatio`](auxiliary-iIntermediateResult.md#scaledownratio) | The scale down ratio. |
| [`frameId`](auxiliary-iIntermediateResult.md#frameid) | The ID of the operated frame. |
| [`rpmColourArgumentIndex`](auxiliary-iIntermediateResult.md#rpmcolourargumentindex) | The index of the rpm colour argument. |

## [iContour](auxiliary-iContour.md)

`contour` is one of the [`results`](#intermediateresult) type in `IntermediateResult`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iContour : NSObject
```
2. 
```swift
class iContour : NSObject
```

| Attribute | Description |
|---------- | ----------- |
| [`pointsCount`](auxiliary-iContour.md#pointscount) | The total points count of the contour. |
| [`points`](auxiliary-iContour.md#points) | The points array of the points that surround the barcode area. |

## [iImageData](auxiliary-iImageData.md)

`ImageData` is one of the [`results`](#intermediateresult) type in `IntermediateResult`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iImageData : NSObject
```
2. 
```swift
class iImageData : NSObject
```

| Attribute | Descriptions |
|---------- | ----------- |
| [`bytes`](auxiliary-iImageData.md#bytes) | The image data content in a byte array. |
| [`bytesLength`](auxiliary-iImageData.md#byteslength) | The length of the image data byte array. |
| [`width`](auxiliary-iImageData.md#width) | The width of the image in pixels. |
| [`height`](auxiliary-iImageData.md#height) | The height of the image in pixels. |
| [`stride`](auxiliary-iImageData.md#stride) | The stride (or scan width) of the image. |
| [`format`](auxiliary-iImageData.md#format) | The image pixel format used in the image byte array. |

## [iLineSegment](auxiliary-iLineSegment.md)

`LineSegment` is one of the [`results`](auxiliary-iIntermediateResult.md#results) type in `IntermediateResult`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iLineSegment : NSObject
```
2. 
```swift
class iLineSegment : NSObject
```

| Attribute | Descriptions |
|---------- | ----------- |
| [`startPoint`](auxiliary-iLineSegment.md#startpoint) | The start point of the line segment. |
| [`endPoint`](auxiliary-iLineSegment.md#endpoint) | The end point of the line segment. |
| [`linesConfidenceCoefficients`](auxiliary-iLineSegment.md#linesconfidencecoefficients) | The confidence coefficients for lines. |

## [iRegionOfInterest](auxiliary-iRegionOfInterest.md)

`RegionOfInterest` is one of the [`results`](auxiliary-iIntermediateResult.md#results) type in `IntermediateResult`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iRegionOfInterest : NSObject
```
2. 
```swift
class iRegionOfInterest : NSObject
```

| Attribute | Descriptions |
|---------- | ----------- |
| [`roiId`](auxiliary-iRegionOfInterest.md#roiid) | The ID generated by the SDK. |
| [`point`](auxiliary-iRegionOfInterest.md#point) | The left top point of the region. |
| [`width`](auxiliary-iRegionOfInterest.md#width) | The width of the region. |
| [`height`](auxiliary-iRegionOfInterest.md#height) | The height of the region. |

## iLocalizationResult

View more in [TextResult >> LocalizationResult](auxiliary-iLocalizationResult.md)

`LocalizationResult` can be the extension of the class [`IntermediateResult`](auxiliary-iIntermediateResult.md). It stores the localization result information.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iLocalizationResult : NSObject
```
2. 
```swift
class iLocalizationResult : NSObject
```

| Attribute | Description |
|---------- | ----------- |
| [`terminatePhase`](auxiliary-iLocalizationResult.md#terminatephase) | The terminate phase of localization result. |
| [`barcodeFormat`](auxiliary-iLocalizationResult.md#barcodeformat) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](auxiliary-iLocalizationResult.md#barcodeformatstring) | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](auxiliary-iLocalizationResult.md#barcodeformat_2 ) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](auxiliary-iLocalizationResult.md#barcodeformatstring_2) | Barcode type in BarcodeFormat group 2 as string. |
| [`resultPoints`](auxiliary-iLocalizationResult.md#resultpoints) | The vertices coordinates information of the barcode region. |
| [`angle`](auxiliary-iLocalizationResult.md#angle) | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](auxiliary-iLocalizationResult.md#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](auxiliary-iLocalizationResult.md#pagenumber) | The page number the barcode located in. The index is 0-based. |
| [`regionName`](auxiliary-iLocalizationResult.md#regionname) | The region name the barcode located in. |
| [`documentName`](auxiliary-iLocalizationResult.md#documentname) | The document name. |
| [`resultCoordinateType`](auxiliary-iLocalizationResult.md#resultcoordinatetype) | The coordinate type. |
| [`accompanyingTextBytes`](auxiliary-iLocalizationResult.md#accompanyingtextbytes) | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](auxiliary-iLocalizationResult.md#accompanyingtextbyteslength) | The length of the accompanying text byte array. |
| [`confidence`](auxiliary-iLocalizationResult.md#confidence) | The confidence of the localization result. |
