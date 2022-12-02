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
| [`dataType`](#datatype) | [`EnumIMResultDataType`]({{ site.mobile_enum }}im-result-data-type.html?lang=objc,swift) | The data type of the intermediate result. |
| [`resultType`](#resulttype) | [`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=objc,swift) | Intermediate result type. |
| [`barcodeComplementMode`](#barcodecomplementmode) | [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) | The [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`bcmIndex`](#bcmindex) | *NSInteger* | The array index of current used [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) in the [`barcodeComplementModes`](auxiliary-iFurtherModes.md#barcodecomplementmodes) setting. |
| [`deformationResistingMode`](#deformationresistingmode) | [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) | The [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`drmIndex`](#drmindex) | *NSInteger* | The array index of current used [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) in the [`deformationResistingModes`](auxiliary-iFurtherModes.md#deformationresistingmodes) setting. |
| [`dpmCodeReadingMode`](#dpmcodereadingmode) | [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) | The [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`dpmcrmIndex`](#dpmcrmindex) | *NSInteger* | The array index of current used [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) in the [`dpmCodeReadingModes`](auxiliary-iFurtherModes.md#dpmcodereadingmodes) setting. |
| [`transformationMatrix`](#transformationmatrix) | *NSArray \** | The rotation matrix. |
| [`textFilterMode`](#textfiltermode) | [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) | The [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`tfmIndex`](#tfmindex) | *NSInteger* | The array index of current used [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) in the [`textFilterModes`](auxiliary-iFurtherModes.md#textfiltermodes) setting. |
| [`localizationMode`](#localizationmode) | [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) | The [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`lmIndex`](#lmindex) | *NSInteger* | The array index of current used [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) in the [`localizationModes`](auxiliary-iPublicRuntimeSettings.md#localizationmodes) setting. |
| [`binarizationMode`](#binarizationmode) | [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) | The [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`bmIndex`](#bmindex) | *NSInteger* | The array index of current used [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) in the [`binarizationModes`](auxiliary-iPublicRuntimeSettings.md#binarizationmodes) setting. |
| [`imagePreprocessingMode`](#imagepreprocessingmode) | [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) | The [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`ipmIndex`](#ipmindex) | *NSInteger* | The array index of current used [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) in [`imagePreprocessingModes`](auxiliary-iFurtherModes.md#imagepreprocessingmodes) setting. |
| [`roiId`](#roiid) | *NSInteger* | The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image. |
| [`regionPredetectionMode`](#regionpredetectionmode) | [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) | The [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`rpmIndex`](#rpmindex) | *NSInteger* | The array index of current used [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) in the [`regionPredetectionModes`](auxiliary-iFurtherModes.md#regionpredetectionmodes) setting. |
| [`grayscaleTransformationMode`](#grayscaletransformationmode) | [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) | The [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`gtmIndex`](#gtmindex) | *NSInteger* | The array index of current used [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) in the [`grayscaleTransformationModes`](auxiliary-iFurtherModes.md#grayscaletransformationmodes) setting. |
| [`colourConversionMode`](#colourconversionmode) | [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) | The [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`cicmIndex`](#cicmindex) | *NSInteger* | The array index of current used [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) in the [`colourConversionModes`](auxiliary-iFurtherModes.md#colourconversionmodes) setting. |
| [`colourClusteringMode`](#colourclusteringmode) | [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) | The [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) used when generating the current intermediate result. |
| [`ccmIndex`](#ccmindex) | *NSInteger* | The array index of current used [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) in the [`colourClusteringModes`](auxiliary-iFurtherModes.md#colourclusteringmodes) setting. |
| [`scaleDownRatio`](#scaledownratio) | *NSInteger* | The scale down ratio. |
| [`frameId`](#frameid) | *NSInteger* | The ID of the operated frame. |
| [`rpmColourArgumentIndex`](#rpmcolourargumentindex) | *NSInteger* | The index of the rpm colour argument. |

## resultsCount

The total result count.

```objc
@property (nonatomic, assign) NSInteger resultsCount
```

## results

One of the following types: Array of [`iContour`](auxiliary-iContour.md), Array of [`iImageData`](auxiliary-iImageData.md), Array of [`iLineSegment`](auxiliary-iLineSegment.md), Array of [`iLocalizationResult`](auxiliary-iLocalizationResult.md), Array of [`iRegionOfInterest`](auxiliary-iRegionOfInterest.md).

```objc
@property (nonatomic, nullable) NSObject* results
```

## dataType

The data type of the intermediate result

```objc
@property (nonatomic, assign) EnumIMResultDataType dataType
```

## resultType

Intermediate result type.

```objc
@property (nonatomic, assign) EnumIntermediateResultType resultType
```

## barcodeComplementMode

The [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumBarcodeComplementMode barcodeComplementMode
```

## bcmIndex

The array index of current used [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) in the [`barcodeComplementModes`](auxiliary-iFurtherModes.md#barcodecomplementmodes) setting.

```objc
@property (nonatomic, assign) NSInteger bcmIndex
```

## deformationResistingMode

The [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumDeformationResistingMode deformationResistingMode
```

## drmIndex

The array index of current used [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) in the [`deformationResistingModes`](auxiliary-iFurtherModes.md#deformationresistingmodes) setting.

```objc
@property (nonatomic, assign) NSInteger drmIndex
```

## dpmCodeReadingMode

The [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumDPMCodeReadingMode dpmCodeReadingMode
```

## dpmcrmIndex

The array index of current used [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) in the [`dpmCodeReadingModes`](auxiliary-iFurtherModes.md#dpmcodereadingmodes) setting.

```objc
@property (nonatomic, assign) NSInteger dpmcrmIndex
```

## transformationMatrix

The rotation matrix.

```objc
@property (nonatomic, nonnull) NSArray* transformationMatrix
```

## textFilterMode

The [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumTextFilterMode textFilterMode
```

## tfmIndex

The array index of current used [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) in the [`textFilterModes`](auxiliary-iFurtherModes.md#textfiltermodes) setting.

```objc
NSInteger tfmIndex
```

## localizationMode

The [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumLocalizationMode localizationMode
```

## lmIndex

The array index of current used [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) in the [`localizationModes`](auxiliary-iPublicRuntimeSettings.md#localizationmodes) setting.

```objc
@property (nonatomic, assign) NSInteger lmIndex
```

## binarizationMode

The [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumBinarizationMode binarizationMode
```

## bmIndex

The array index of current used [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) in the [`binarizationModes`](auxiliary-iPublicRuntimeSettings.md#binarizationmodes) setting.

```objc
@property (nonatomic, assign) NSInteger bmIndex
```

## imagePreprocessingMode

The [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumImagePreprocessingMode imagePreprocessingMode
```

## ipmIndex

The array index of current used [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) in [`imagePreprocessingModes`](auxiliary-iFurtherModes.md#imagepreprocessingmodes) setting.

```objc
@property (nonatomic, assign) NSInteger ipmIndex
```

## roiId

The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image.

```objc
@property (nonatomic, assign) NSInteger roiId
```

## regionPredetectionMode

The [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumRegionPredetectionMode regionPredetectionMode
```

## rpmIndex

The array index of current used [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) in the [`regionPredetectionModes`](auxiliary-iFurtherModes.md#regionpredetectionmodes) setting.

```objc
@property (nonatomic, assign) NSInteger rpmIndex
```

## grayscaleTransformationMode

The [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumGrayscaleTransformationMode grayscaleTransformationMode
```

## gtmIndex

The array index of current used [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) in the [`grayscaleTransformationModes`](auxiliary-iFurtherModes.md#grayscaletransformationmodes) setting.

```objc
@property (nonatomic, assign) NSInteger gtmIndex
```

## colourConversionMode

The [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumColourConversionMode colourConversionMode
```

## cicmIndex

The array index of current used [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) in the [`colourConversionModes`](auxiliary-iFurtherModes.md#colourconversionmodes) setting.

```objc
@property (nonatomic, assign) NSInteger cicmIndex
```

## colourClusteringMode

The [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) used when generating the current intermediate result.

```objc
@property (nonatomic, assign) EnumColourClusteringMode colourClusteringMode
```

## ccmIndex

The array index of current used [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) in the [`colourClusteringModes`](auxiliary-iFurtherModes.md#colourclusteringmodes) setting.

```objc
@property (nonatomic, assign) NSInteger ccmIndex
```

## scaleDownRatio

The scale down ratio.

```objc
@property (nonatomic, assign) NSInteger scaleDownRatio
```

## frameId

The ID of the operated frame.

```objc
@property (nonatomic, assign) NSInteger frameId
```

## rpmColourArgumentIndex

The index of the rpm colour argument.

```objc
@property (nonatomic, assign) NSInteger rpmColourArgumentIndex
```
