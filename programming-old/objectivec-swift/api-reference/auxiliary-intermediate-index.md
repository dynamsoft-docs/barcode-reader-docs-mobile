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
permalink: /programming/objectivec-swift/api-reference/auxiliary-intermediate-index.html
---

# Intermediate Result Classes

## [iIntermediateResult](auxiliary-iIntermediateResult.html)

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
| [`resultsCount`](auxiliary-iIntermediateResult.html#resultscount) | The total result count. |
| [`results`](auxiliary-iIntermediateResult.html#results) | One of the following types: Array of [`iContour`](auxiliary-iContour.html), Array of [`iImageData`](auxiliary-iImageData.html), Array of [`iLineSegment`](auxiliary-iLineSegment.html), Array of [`iLocalizationResult`](auxiliary-iLocalizationResult.html), Array of [`iRegionOfInterest`](auxiliary-iRegionOfInterest.html). |
| [`dataType`](auxiliary-iIntermediateResult.html#datatype) | The data type of the intermediate result. |
| [`resultType`](auxiliary-iIntermediateResult.html#resulttype) | Intermediate result type. |
| [`barcodeComplementMode`](auxiliary-iIntermediateResult.html#barcodecomplementmode) | The [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`bcmIndex`](auxiliary-iIntermediateResult.html#bcmindex) | The array index of current used [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) in the [`barcodeComplementModes`](auxiliary-iFurtherModes.html#barcodecomplementmodes) setting. |
| [`deformationResistingMode`](auxiliary-iIntermediateResult.html#deformationresistingmode) | The [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`drmIndex`](auxiliary-iIntermediateResult.html#drmindex) | The array index of current used [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) in the [`deformationResistingModes`](auxiliary-iFurtherModes.html#deformationresistingmodes) setting. |
| [`dpmCodeReadingMode`](auxiliary-iIntermediateResult.html#dpmcodereadingmode) | The [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`dpmcrmIndex`](auxiliary-iIntermediateResult.html#dpmcrmindex) | The array index of current used [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) in the [`dpmCodeReadingModes`](auxiliary-iFurtherModes.html#dpmcodereadingmodes) setting. |
| [`transformationMatrix`](auxiliary-iIntermediateResult.html#transformationMatrix) | The rotation matrix. |
| [`textFilterMode`](auxiliary-iIntermediateResult.html#textfiltermode) | The [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`tfmIndex`](auxiliary-iIntermediateResult.html#tfmindex) | The array index of current used [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) in the [`textFilterModes`](auxiliary-iFurtherModes.html#textfiltermodes) setting. |
| [`localizationMode`](auxiliary-iIntermediateResult.html#localizationmode) | The [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`lmIndex`](auxiliary-iIntermediateResult.html#lmindex) | The array index of current used [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) in the [`localizationModes`](auxiliary-iPublicRuntimeSettings.html#localizationmodes) setting. |
| [`binarizationMode`](auxiliary-iIntermediateResult.html#binarizationmode) | The [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`bmIndex`](auxiliary-iIntermediateResult.html#bmindex) | The array index of current used [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) in the [`binarizationModes`](auxiliary-iPublicRuntimeSettings.html#binarizationmodes) setting. |
| [`imagePreprocessingMode`](auxiliary-iIntermediateResult.html#imagepreprocessingmode) | The [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`ipmIndex`](auxiliary-iIntermediateResult.html#ipmindex) | The array index of current used [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) in [`imagePreprocessingModes`](auxiliary-iFurtherModes.html#imagepreprocessingmodes) setting. |
| [`roiId`](auxiliary-iIntermediateResult.html#roiid) | The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image. |
| [`regionPredetectionMode`](auxiliary-iIntermediateResult.html#regionpredetectionmode) | The [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`rpmIndex`](auxiliary-iIntermediateResult.html#rpmindex) | The array index of current used [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) in the [`regionPredetectionModes`](auxiliary-iFurtherModes.html#regionpredetectionmodes) setting. |
| [`grayscaleTransformationMode`](auxiliary-iIntermediateResult.html#grayscaletransformationmode) | The [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`gtmIndex`](auxiliary-iIntermediateResult.html#gtmindex) | The array index of current used [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) in the [`grayscaleTransformationModes`](auxiliary-iFurtherModes.html#grayscaletransformationmodes) setting. |
| [`colourConversionMode`](auxiliary-iIntermediateResult.html#colourconversionmode) | The [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`cicmIndex`](auxiliary-iIntermediateResult.html#cicmindex) | The array index of current used [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) in the [`colourConversionModes`](auxiliary-iFurtherModes.html#colourconversionmodes) setting. |
| [`colourClusteringMode`](auxiliary-iIntermediateResult.html#colourclusteringmode) | The [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`ccmIndex`](auxiliary-iIntermediateResult.html#ccmindex) | The array index of current used [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) in the [`colourClusteringModes`](auxiliary-iFurtherModes.html#colourclusteringmodes) setting. |
| [`scaleDownRatio`](auxiliary-iIntermediateResult.html#scaledownratio) | The scale down ratio. |
| [`frameId`](auxiliary-iIntermediateResult.html#frameid) | The ID of the operated frame. |
| [`rpmColourArgumentIndex`](auxiliary-iIntermediateResult.html#rpmcolourargumentindex) | The index of the rpm colour argument. |

## [iContour](auxiliary-iContour.html)

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
| [`pointsCount`](auxiliary-iContour.html#pointscount) | The total points count of the contour. |
| [`points`](auxiliary-iContour.html#points) | The points array of the points that surround the barcode area. |

## [iImageData](auxiliary-iImageData.html)

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
| [`bytes`](auxiliary-iImageData.html#bytes) | The image data content in a byte array. |
| [`bytesLength`](auxiliary-iImageData.html#byteslength) | The length of the image data byte array. |
| [`width`](auxiliary-iImageData.html#width) | The width of the image in pixels. |
| [`height`](auxiliary-iImageData.html#height) | The height of the image in pixels. |
| [`stride`](auxiliary-iImageData.html#stride) | The stride (or scan width) of the image. |
| [`format`](auxiliary-iImageData.html#format) | The image pixel format used in the image byte array. |

## [iLineSegment](auxiliary-iLineSegment.html)

`LineSegment` is one of the [`results`](auxiliary-iIntermediateResult.html#results) type in `IntermediateResult`.

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
| [`startPoint`](auxiliary-iLineSegment.html#startpoint) | The start point of the line segment. |
| [`endPoint`](auxiliary-iLineSegment.html#endpoint) | The end point of the line segment. |
| [`linesConfidenceCoefficients`](auxiliary-iLineSegment.html#linesconfidencecoefficients) | The confidence coefficients for lines. |

## [iRegionOfInterest](auxiliary-iRegionOfInterest.html)

`RegionOfInterest` is one of the [`results`](auxiliary-iIntermediateResult.html#results) type in `IntermediateResult`.

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
| [`roiId`](auxiliary-iRegionOfInterest.html#roiid) | The ID generated by the SDK. |
| [`point`](auxiliary-iRegionOfInterest.html#point) | The left top point of the region. |
| [`width`](auxiliary-iRegionOfInterest.html#width) | The width of the region. |
| [`height`](auxiliary-iRegionOfInterest.html#height) | The height of the region. |

## iLocalizationResult

View more in [TextResult >> LocalizationResult](auxiliary-iLocalizationResult.html)

`LocalizationResult` can be the extension of the class [`IntermediateResult`](auxiliary-iIntermediateResult.html). It stores the localization result information.

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
| [`terminatePhase`](auxiliary-iLocalizationResult.html#terminatephase) | The terminate phase of localization result. |
| [`barcodeFormat`](auxiliary-iLocalizationResult.html#barcodeformat) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](auxiliary-iLocalizationResult.html#barcodeformatstring) | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](auxiliary-iLocalizationResult.html#barcodeformat_2 ) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](auxiliary-iLocalizationResult.html#barcodeformatstring_2) | Barcode type in BarcodeFormat group 2 as string. |
| [`resultPoints`](auxiliary-iLocalizationResult.html#resultpoints) | The vertices coordinates information of the barcode region. |
| [`angle`](auxiliary-iLocalizationResult.html#angle) | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](auxiliary-iLocalizationResult.html#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](auxiliary-iLocalizationResult.html#pagenumber) | The page number the barcode located in. The index is 0-based. |
| [`regionName`](auxiliary-iLocalizationResult.html#regionname) | The region name the barcode located in. |
| [`documentName`](auxiliary-iLocalizationResult.html#documentname) | The document name. |
| [`resultCoordinateType`](auxiliary-iLocalizationResult.html#resultcoordinatetype) | The coordinate type. |
| [`accompanyingTextBytes`](auxiliary-iLocalizationResult.html#accompanyingtextbytes) | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](auxiliary-iLocalizationResult.html#accompanyingtextbyteslength) | The length of the accompanying text byte array. |
| [`confidence`](auxiliary-iLocalizationResult.html#confidence) | The confidence of the localization result. |
