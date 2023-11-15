---
layout: default-layout
title: Parameter Configurations - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the Parameter Configurations of Dynamsoft Barcode Reader for iOS SDK.
keywords: Parameter Configurations, class, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-parameter-index-v8.2.0.html
---

# Parameter Configuration Classes

## [iPublicRuntimeSettings](auxiliary-iPublicRuntimeSettings.html)

You can update most of the parameter settings through the `iPublicRuntimeSettings` class.

```objc
@interface iPublicRuntimeSettings
```  

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`terminatePhase`](auxiliary-iPublicRuntimeSettings.html#terminatephase) | [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift) | Sets the phase to stop the barcode reading algorithm. |
| [`timeout`](auxiliary-iPublicRuntimeSettings.html#timeout) | *NSInteger* | Set the maximum time spent on scanning one image (page). |
| [`maxAlgorithmThreadCount`](auxiliary-iPublicRuntimeSettings.html#maxalgorithmthreadcount) | *NSInteger* | Sets the number of threads the image processing algorithm will use to decode barcodes. |
| [`expectedBarcodesCount`](auxiliary-iPublicRuntimeSettings.html#expectedbarcodescount) | *NSInteger* | Sets the number of barcodes expected to be detected for each image. |
| [`barcodeFormatIds`](auxiliary-iPublicRuntimeSettings.html#barcodeformatids) | *NSInteger* | BarcodeFormat group 1. Read more in [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) |
| [`barcodeFormatIds_2`](auxiliary-iPublicRuntimeSettings.html#barcodeformatids_2) | *NSInteger* | BarcodeFormat group 2. Read more in [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) |
| [`pdfRasterDPI`](auxiliary-iPublicRuntimeSettings.html#pdfrasterdpi) | *NSInteger* | Sets the output image resolution. |
| [`scaleDownThreshold`](auxiliary-iPublicRuntimeSettings.html#scaledownthreshold) | *NSInteger* | Sets the threshold for the image shrinking. |
| [`binarizationModes`](auxiliary-iPublicRuntimeSettings.html#binarizationmodes) | *NSArray\** | Sets the mode and priority for binarization. |
| [`localizationModes`](auxiliary-iPublicRuntimeSettings.html#localizationmodes) | *NSArray\** | Sets the mode and priority for localization algorithms. |
| [`furtherModes`](auxiliary-iPublicRuntimeSettings.html#furthermodes) | [`FurtherModes`](auxiliary-iFurtherModes.html) | Further modes settings. Please read more in [`FurtherModes`](auxiliary-iFurtherModes.html) class. |
| [`deblurLevel`](auxiliary-iPublicRuntimeSettings.html#deblurlevel) | *NSInteger* | Sets the degree of blurriness of the barcode.
 |
| [`intermediateResultTypes`](auxiliary-iPublicRuntimeSettings.html#intermediateresulttypes) | *NSInteger* | Sets which types of intermediate result to be kept for further reference. |
| [`intermediateResultSavingMode`](auxiliary-iPublicRuntimeSettings.html#intermediateresultsavingmode) | [`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=objc,swift) | Sets the mode for saving intermediate result. |
| [`resultCoordinateType`](auxiliary-iPublicRuntimeSettings.html#resultcoordinatetype) | [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift) | Specifies the format for the coordinates returned. |
| [`textResultOrderModes`](auxiliary-iPublicRuntimeSettings.html#textresultordermodes) | *NSArray\** | Sets the mode and priority for the order of the text results returned. |
| [`returnBarcodeZoneClarity`](auxiliary-iPublicRuntimeSettings.html#returnbarcodezoneclarity) | *NSInteger* | Sets whether or not to return the clarity of the barcode zone. |
| [`region`](auxiliary-iPublicRuntimeSettings.html#region) | [`iRegionDefinition`](auxiliary-iRegionDefinition.html) | Sets the scan region. Please read more in [`iRegionDefinition`](auxiliary-iRegionDefinition.html) Class |
| [`minBarcodeTextLength`](auxiliary-iPublicRuntimeSettings.html#minbarcodetextlength) | *NSInteger* | Sets the range of barcode text length for barcodes search. |
| [`minResultConfidence`](auxiliary-iPublicRuntimeSettings.html#minresultconfidence) | *NSInteger* | The minimum confidence of the result. |
| [`scaleUpModes`](auxiliary-iPublicRuntimeSettings.html#scaleupmodes) | *NSArray\**| Sets the mode and priority to control the sampling methods of scale-up for linear barcode with small module sizes. |
| [`pdfReadingMode`](auxiliary-iPublicRuntimeSettings.html#pdfreadingmode) | *NSInteger* | Sets the way to detect barcodes from a PDF file when using the DecodeFile method. |
| [`deblurModes`](auxiliary-iPublicRuntimeSettings.html#deblurmodes) | *NSArray\** | Sets the mode and priority for deblurring. |
| [`barcodeZoneMinDistanceToImageBorders`](auxiliary-iPublicRuntimeSettings.html#barcodezonemindistancetoimageborders) | *NSInteger* | Sets the minimum distance (in pixels) between the barcode zone and image borders. |

## [iFurtherModes](auxiliary-iFurtherModes.html)

`FurtherModes` is an extension of the `PublicRuntimeSettings` class. Through the `FurtherModes`, you can make advanced settings to process the image for barcode reading.

```objc
@interface iFurtherModes
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----- |
| [`colourClusteringModes`](auxiliary-iFurtherModes.html#colourclusteringmodes) | *NSArray*\* | Sets the mode and priority for colour categorization. |
| [`colourConversionModes`](auxiliary-iFurtherModes.html#colourconversionmodes) | *NSArray*\* | Sets the mode and priority for converting a colour image to a grayscale image. |
| [`grayscaleTransformationModes`](auxiliary-iFurtherModes.html#grayscaletransformationmodes) | *NSArray*\* | Sets the mode and priority for the grayscale image conversion. |
| [`regionPredetectionModes`](auxiliary-iFurtherModes.html#regionpredetectionmodes) | *NSArray*\* | Sets the region pre-detection mode for barcodes search. |
| [`imagePreprocessingModes`](auxiliary-iFurtherModes.html#imagepreprocessingmodes) | *NSArray*\* | Sets the mode and priority for image preprocessing algorithms. |
| [`textureDetectionModes`](auxiliary-iFurtherModes.html#texturedetectionmodes) | *NSArray*\* | Sets the mode and priority for texture detection. |
| [`textFilterModes`](auxiliary-iFurtherModes.html#textfiltermodes) | *NSArray*\* | Sets the mode and priority for text filter. |
| [`dpmCodeReadingModes`](auxiliary-iFurtherModes.html#dpmcodereadingmodes) | *NSArray*\* | Sets the mode and priority for DPM code reading. |
| [`deformationResistingModes`](auxiliary-iFurtherModes.html#deformationresistingmodes) | *NSArray*\* | Sets the mode and priority for deformation resisting. |
| [`barcodeComplementModes`](auxiliary-iFurtherModes.html#barcodecomplementmodes) | *NSArray*\* | Sets the mode and priority to complement the missing parts in the barcode. |
| [`barcodeColourModes`](auxiliary-iFurtherModes.html#barcodecolourmodes) | *NSArray*\* | Sets the mode and priority for the barcode colour mode used to process the barcode zone. |
| [`accompanyingTextRecognitionModes`](auxiliary-iFurtherModes.html#accompanyingtextrecognitionmodes) | *NSArray*\* | Sets the mode and priority to recognize accompanying text. |

## [iRegionDefinition](auxiliary-iRegionDefinition.html)

Stores the region information.

```objc
@interface iRegionDefinition
```

| Attribute | Type | Descriptions |
|---------- | ---- | ------------ |
| [`regionTop`](auxiliary-iRegionDefinition.html#regiontop) | *NSInteger* | The top-most coordinate or percentage of the region. |
| [`regionLeft`](auxiliary-iRegionDefinition.html#regionleft) | *NSInteger* | The Left-most coordinate or percentage of the region. |
| [`regionRight`](auxiliary-iRegionDefinition.html#regionright) | *NSInteger* | The Right-most coordinate or percentage of the region. |
| [`regionBottom`](auxiliary-iRegionDefinition.html#regionbottom) | *NSInteger* | The Bottom-most coordinate or percentage of the region. |
| [`regionMeasuredByPercentage`](auxiliary-iRegionDefinition.html#regionmeasuredbypercentage) | *NSInteger* | Sets whether or not to use percentage to measure the region size. |

## [iFrameDecodingParameters](auxiliary-iFrameDecodingParameters.html)

The parameters that helps you on frame decoding.

```objc
@interface iFrameDecodingParameters
```

| Attribute | Type | Descriptions |
|---------- | ---- | ------------ |
| [`maxQueueLength`](auxiliary-iFrameDecodingParameters.html#maxqueuelength) | *NSInteger* | The maximum number of frames waiting for decoding. |
| [`maxResultQueueLength`](auxiliary-iFrameDecodingParameters.html#maxresultqueuelength) | *NSInteger* | The maximum number of frames waiting results (text result/localization result) will be kept for further reference. |
| [`width`](auxiliary-iFrameDecodingParameters.html#width) | *NSInteger* | The width of the frame image in pixels.  |
| [`height`](auxiliary-iFrameDecodingParameters.html#height) | *NSInteger* | The height of the frame image in pixels. |
| [`stride`](auxiliary-iFrameDecodingParameters.html#stride) | *NSInteger* | The stride (or scan width) of the frame image. |
| [`imagePixelFormat`](auxiliary-iFrameDecodingParameters.html#imagepixelformat) | [`EnumImagePixelFormat`]({{ site.mobile_enum }}image-pixel-format.html?lang=objc,swift) | The image pixel format used in the image byte array. |
| [`region`](auxiliary-iFrameDecodingParameters.html#region) | [`iRegionDefinition`](auxiliary-iRegionDefinition.html) | The region definition of the frame to calculate the internal indicator. |
| [`threshold`](auxiliary-iFrameDecodingParameters.html#threshold) | *float* | The threshold used for filtering frames. |
| [`fps`](auxiliary-iFrameDecodingParameters.html#fps) | *NSInteger* | The frequency of calling [`appendFrame`](primary-video.html#appendFrame) per second. |
| [`autoFilter`](auxiliary-iFrameDecodingParameters.html#autofilter) | *NSInteger* | Sets whether to filter frames automatically. |
| [`clarityCalculationMethod`](auxiliary-iFrameDecodingParameters.html#claritycalculationmethod) | `EnumClarityCalculationMethod` | Sets the method used for calculating the clarity of the frames. |
| [`clarityFilterMode`](auxiliary-iFrameDecodingParameters.html#clarityfiltermode) | `EnumClarityFilterMode` | Sets the mode used for filtering frames by calculated clarity. |
