---
layout: default-layout
title: Dynamsoft Barcode Reader Objective-C & Swift API Reference - iIntermediateResult Class
description: This page shows the iIntermediateResult Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iIntermediateResult, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iIntermediateResult.html
---

# Class iIntermediateResult

Stores the intermediate result.

```objc
@interface iIntermediateResult 
```  

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`resultsCount`](#resultscount) | *NSInteger* | The total result count. |
| [`results`](#results) | *NSObject\** | One of the following types: Array of [`iContour`](auxiliary-iContour.md), Array of [`iImageData`](auxiliary-iImageData.md), Array of [`iLineSegment`](auxiliary-iLineSegment.md), Array of [`iLocalizationResult`](auxiliary-iLocalizationResult.md), Array of [`iRegionOfInterest`](auxiliary-iRegionOfInterest.md). |
| [`dataType`](#datatype) | [`EnumIMResultDataType`]({{ site.mobile-enum }}im-result-data-type.html) | The data type of the intermediate result. |
| [`resultType`](#resulttype) | [`EnumIntermediateResultType`]({{ site.mobile-enum }}intermediate-result-type.html) | Intermediate result type. |
| [`barcodeComplementMode`](#barcodecomplementmode) | [`EnumBarcodeComplementMode`]({{ site.mobile-enum }}barcode-complement-mode.html) | The [`EnumBarcodeComplementMode`]({{ site.mobile-enum }}barcode-complement-mode.html) used when generating the current intermediate result. |
| [`bcmIndex`](#bcmindex) | *NSInteger* | The array index of current used [`EnumBarcodeComplementMode`]({{ site.mobile-enum }}barcode-complement-mode.html) in the [`barcodeComplementModes`](auxiliary-iFurtherModes.md#barcodecomplementmodes) setting. |
| [`deformationResistingMode`](#deformationresistingmode) | [`EnumDeformationResistingMode`]({{ site.mobile-enum }}deformation-resisting-mode.html) | The [`EnumDeformationResistingMode`]({{ site.mobile-enum }}deformation-resisting-mode.html) used when generating the current intermediate result. |
| [`drmIndex`](#drmindex) | *NSInteger* | The array index of current used [`EnumDeformationResistingMode`]({{ site.mobile-enum }}deformation-resisting-mode.html) in the [`deformationResistingModes`](auxiliary-iFurtherModes.md#deformationresistingmodes) setting. |
| [`dpmCodeReadingMode`](#dpmcodereadingmode) | [`EnumDPMCodeReadingMode`]({{ site.mobile-enum }}dpm-code-reading-mode.html) | The [`EnumDPMCodeReadingMode`]({{ site.mobile-enum }}dpm-code-reading-mode.html) used when generating the current intermediate result. |
| [`dpmcrmIndex`](#dpmcrmindex) | *NSInteger* | The array index of current used [`EnumDPMCodeReadingMode`]({{ site.mobile-enum }}dpm-code-reading-mode.html) in the [`dpmCodeReadingModes`](auxiliary-iFurtherModes.md#dpmcodereadingmodes) setting. |
| [`transformationMatrix`](#transformationMatrix) | *NSArray \** | The rotation matrix. |
| [`textFilterMode`](#textfiltermode) | [`EnumTextFilterMode`]({{ site.mobile-enum }}text-filter-mode.html) | The [`EnumTextFilterMode`]({{ site.mobile-enum }}text-filter-mode.html) used when generating the current intermediate result. |
| [`tfmIndex`](#tfmindex) | *NSInteger* | The array index of current used [`EnumTextFilterMode`]({{ site.mobile-enum }}text-filter-mode.html) in the [`textFilterModes`](auxiliary-iFurtherModes.md#textfiltermodes) setting. |
| [`localizationMode`](#localizationmode) | [`EnumLocalizationMode`]({{ site.mobile-enum }}localization-mode.html) | The [`EnumLocalizationMode`]({{ site.mobile-enum }}localization-mode.html) used when generating the current intermediate result. |
| [`lmIndex`](#lmindex) | *NSInteger* | The array index of current used [`EnumLocalizationMode`]({{ site.mobile-enum }}localization-mode.html) in the [`localizationModes`](auxiliary-iPublicRuntimeSettings.md#localizationmodes) setting. |
| [`binarizationMode`](#binarizationmode) | [`EnumBinarizationMode`]({{ site.mobile-enum }}binarization-mode.html) | The [`EnumBinarizationMode`]({{ site.mobile-enum }}binarization-mode.html) used when generating the current intermediate result. |
| [`bmIndex`](#bmindex) | *NSInteger* | The array index of current used [`EnumBinarizationMode`]({{ site.mobile-enum }}binarization-mode.html) in the [`binarizationModes`](auxiliary-iPublicRuntimeSettings.md#binarizationmodes) setting. |
| [`imagePreprocessingMode`](#imagepreprocessingmode) | [`EnumImagePreprocessingMode`]({{ site.mobile-enum }}image-preprocessing-mode.html) | The [`EnumImagePreprocessingMode`]({{ site.mobile-enum }}image-preprocessing-mode.html) used when generating the current intermediate result. |
| [`ipmIndex`](#ipmindex) | *NSInteger* | The array index of current used [`EnumImagePreprocessingMode`]({{ site.mobile-enum }}image-preprocessing-mode.html) in [`imagePreprocessingModes`](auxiliary-iFurtherModes.md#imagepreprocessingmodes) setting. |
| [`roiId`](#roiid) | *NSInteger* | The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image. |
| [`regionPredetectionMode`](#regionpredetectionmode) | [`EnumRegionPredetectionMode`]({{ site.mobile-enum }}region-predetection-mode.html) | The [`EnumRegionPredetectionMode`]({{ site.mobile-enum }}region-predetection-mode.html) used when generating the current intermediate result. |
| [`rpmIndex`](#rpmindex) | *NSInteger* | The array index of current used [`EnumRegionPredetectionMode`]({{ site.mobile-enum }}region-predetection-mode.html) in the [`regionPredetectionModes`](auxiliary-iFurtherModes.md#regionpredetectionmodes) setting. |
| [`grayscaleTransformationMode`](#grayscaletransformationmode) | [`EnumGrayscaleTransformationMode`]({{ site.mobile-enum }}grayscale-transformation-mode.html) | The [`EnumGrayscaleTransformationMode`]({{ site.mobile-enum }}grayscale-transformation-mode.html) used when generating the current intermediate result. |
| [`gtmIndex`](#gtmindex) | *NSInteger* | The array index of current used [`EnumGrayscaleTransformationMode`]({{ site.mobile-enum }}grayscale-transformation-mode.html) in the [`grayscaleTransformationModes`](auxiliary-iFurtherModes.md#grayscaletransformationmodes) setting. |
| [`colourConversionMode`](#colourconversionmode) | [`EnumColourConversionMode`]({{ site.mobile-enum }}colour-conversion-mode.html) | The [`EnumColourConversionMode`]({{ site.mobile-enum }}colour-conversion-mode.html) used when generating the current intermediate result. |
| [`cicmIndex`](#cicmindex) | *NSInteger* | The array index of current used [`EnumColourConversionMode`]({{ site.mobile-enum }}colour-conversion-mode.html) in the [`colourConversionModes`](auxiliary-iFurtherModes.md#colourconversionmodes) setting. |
| [`colourClusteringMode`](#colourclusteringmode) | [`EnumColourClusteringMode`]({{ site.mobile-enum }}colour-clustering-mode.html) | The [`EnumColourClusteringMode`]({{ site.mobile-enum }}colour-clustering-mode.html) used when generating the current intermediate result. |
| [`ccmIndex`](#ccmindex) | *NSInteger* | The array index of current used [`EnumColourClusteringMode`]({{ site.mobile-enum }}colour-clustering-mode.html) in the [`colourClusteringModes`](auxiliary-iFurtherModes.md#colourclusteringmodes) setting. |
| [`scaleDownRatio`](#scaledownratio) | *NSInteger* | The scale down ratio. |
| [`frameId`](#frameid) | *NSInteger* | The ID of the operated frame. |
| [`rpmColourArgumentIndex`](#rpmcolourargumentindex) | *NSInteger* | The index of the rpm colour argument. |

## resultsCount

The total result count.

```objc
NSInteger resultsCount
```

## results

One of the following types: Array of [`iContour`](auxiliary-iContour.md), Array of [`iImageData`](auxiliary-iImageData.md), Array of [`iLineSegment`](auxiliary-iLineSegment.md), Array of [`iLocalizationResult`](auxiliary-iLocalizationResult.md), Array of [`iRegionOfInterest`](auxiliary-iRegionOfInterest.md).

```objc
NSObject* results
```

## dataType

The data type of the intermediate result

```objc
EnumIMResultDataType dataType
```

## resultType

Intermediate result type.

```objc
EnumIntermediateResultType resultType
```

## barcodeComplementMode

The [`EnumBarcodeComplementMode`]({{ site.mobile-enum }}barcode-complement-mode.html) used when generating the current intermediate result.

```objc
EnumBarcodeComplementMode barcodeComplementMode
```

## bcmIndex

The array index of current used [`EnumBarcodeComplementMode`]({{ site.mobile-enum }}barcode-complement-mode.html) in the [`barcodeComplementModes`](auxiliary-iFurtherModes.md#barcodecomplementmodes) setting.

```objc
NSInteger bcmIndex
```

## deformationResistingMode

The [`EnumDeformationResistingMode`]({{ site.mobile-enum }}deformation-resisting-mode.html) used when generating the current intermediate result.

```objc
EnumDeformationResistingMode deformationResistingMode
```

## drmIndex

The array index of current used [`EnumDeformationResistingMode`]({{ site.mobile-enum }}deformation-resisting-mode.html) in the [`deformationResistingModes`](auxiliary-iFurtherModes.md#deformationresistingmodes) setting.

```objc
NSInteger drmIndex
```

## dpmCodeReadingMode

The [`EnumDPMCodeReadingMode`]({{ site.mobile-enum }}dpm-code-reading-mode.html) used when generating the current intermediate result.

```objc
EnumDPMCodeReadingMode dpmCodeReadingMode
```

## dpmcrmIndex

The array index of current used [`EnumDPMCodeReadingMode`]({{ site.mobile-enum }}dpm-code-reading-mode.html) in the [`dpmCodeReadingModes`](auxiliary-iFurtherModes.md#dpmcodereadingmodes) setting.

```objc
NSInteger dpmcrmIndex
```

## transformationMatrix

The rotation matrix.

```objc
NSArray* transformationMatrix[9]
```

## textFilterMode

The [`EnumTextFilterMode`]({{ site.mobile-enum }}text-filter-mode.html) used when generating the current intermediate result.

```objc
EnumTextFilterMode textFilterMode
```

## tfmIndex

The array index of current used [`EnumTextFilterMode`]({{ site.mobile-enum }}text-filter-mode.html) in the [`textFilterModes`](auxiliary-iFurtherModes.md#textfiltermodes) setting.

```objc
NSInteger tfmIndex
```

## localizationMode

The [`EnumLocalizationMode`]({{ site.mobile-enum }}localization-mode.html) used when generating the current intermediate result.

```objc
EnumLocalizationMode localizationMode
```

## lmIndex

The array index of current used [`EnumLocalizationMode`]({{ site.mobile-enum }}localization-mode.html) in the [`localizationModes`](auxiliary-iPublicRuntimeSettings.md#localizationmodes) setting.

```objc
NSInteger lmIndex
```

## binarizationMode

The [`EnumBinarizationMode`]({{ site.mobile-enum }}binarization-mode.html) used when generating the current intermediate result.

```objc
EnumBinarizationMode binarizationMode
```

## bmIndex

The array index of current used [`EnumBinarizationMode`]({{ site.mobile-enum }}binarization-mode.html) in the [`binarizationModes`](auxiliary-iPublicRuntimeSettings.md#binarizationmodes) setting.

```objc
NSInteger bmIndex
```

## imagePreprocessingMode

The [`EnumImagePreprocessingMode`]({{ site.mobile-enum }}image-preprocessing-mode.html) used when generating the current intermediate result.

```objc
EnumImagePreprocessingMode imagePreprocessingMode
```

## ipmIndex

The array index of current used [`EnumImagePreprocessingMode`]({{ site.mobile-enum }}image-preprocessing-mode.html) in [`imagePreprocessingModes`](auxiliary-iFurtherModes.md#imagepreprocessingmodes) setting.

```objc
NSInteger ipmIndex
```

## roiId

The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image.

```objc
NSInteger roiId
```

## regionPredetectionMode

The [`EnumRegionPredetectionMode`]({{ site.mobile-enum }}region-predetection-mode.html) used when generating the current intermediate result.

```objc
EnumRegionPredetectionMode regionPredetectionMode
```

## rpmIndex

The array index of current used [`EnumRegionPredetectionMode`]({{ site.mobile-enum }}region-predetection-mode.html) in the [`regionPredetectionModes`](auxiliary-iFurtherModes.md#regionpredetectionmodes) setting.

```objc
NSInteger rpmIndex
```

## grayscaleTransformationMode

The [`EnumGrayscaleTransformationMode`]({{ site.mobile-enum }}grayscale-transformation-mode.html) used when generating the current intermediate result.

```objc
EnumGrayscaleTransformationMode grayscaleTransformationMode
```

## gtmIndex

The array index of current used [`EnumGrayscaleTransformationMode`]({{ site.mobile-enum }}grayscale-transformation-mode.html) in the [`grayscaleTransformationModes`](auxiliary-iFurtherModes.md#grayscaletransformationmodes) setting.

```objc
NSInteger gtmIndex
```

## colourConversionMode

The [`EnumColourConversionMode`]({{ site.mobile-enum }}colour-conversion-mode.html) used when generating the current intermediate result.

```objc
EnumColourConversionMode colourConversionMode
```

## cicmIndex

The array index of current used [`EnumColourConversionMode`]({{ site.mobile-enum }}colour-conversion-mode.html) in the [`colourConversionModes`](auxiliary-iFurtherModes.md#colourconversionmodes) setting.

```objc
NSInteger cicmIndex
```

## colourClusteringMode

The [`EnumColourClusteringMode`]({{ site.mobile-enum }}colour-clustering-mode.html) used when generating the current intermediate result.

```objc
EnumColourClusteringMode colourClusteringMode
```

## ccmIndex

The array index of current used [`EnumColourClusteringMode`]({{ site.mobile-enum }}colour-clustering-mode.html) in the [`colourClusteringModes`](auxiliary-iFurtherModes.md#colourclusteringmodes) setting.

```objc
NSInteger ccmIndex
```

## scaleDownRatio

The scale down ratio.

```objc
NSInteger scaleDownRatio
```

## frameId

The ID of the operated frame.

```objc
NSInteger frameId
```

## rpmColourArgumentIndex

The index of the rpm colour argument.

```objc
NSInteger rpmColourArgumentIndex
```
