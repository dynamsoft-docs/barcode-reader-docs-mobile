---
layout: default-layout
title: Parameter Configurations - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the Parameter Configurations of Dynamsoft Barcode Reader for iOS SDK.
keywords: Parameter Configurations, class, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-parameter-index.html
---

# Parameter Configuration Classes

## [iPublicRuntimeSettings](auxiliary-iPublicRuntimeSettings.md)

You can update most of the parameter settings through the `iPublicRuntimeSettings` class.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iPublicRuntimeSettings : NSObject
```
2. 
```swift
class iPublicRuntimeSettings : NSObject
```

| Attribute | Descriptions |
|---------- | ----------- |
| [`terminatePhase`](auxiliary-iPublicRuntimeSettings.md#terminatephase) | Sets the phase to stop the barcode reading algorithm. |
| [`timeout`](auxiliary-iPublicRuntimeSettings.md#timeout) | Set the maximum time spent on scanning one image (page). |
| [`maxAlgorithmThreadCount`](auxiliary-iPublicRuntimeSettings.md#maxalgorithmthreadcount) | Sets the number of threads the image processing algorithm will use to decode barcodes. |
| [`expectedBarcodesCount`](auxiliary-iPublicRuntimeSettings.md#expectedbarcodescount) | Sets the number of barcodes expected to be detected for each image. |
| [`barcodeFormatIds`](auxiliary-iPublicRuntimeSettings.md#barcodeformatids) | BarcodeFormat group 1. Read more in [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) |
| [`barcodeFormatIds_2`](auxiliary-iPublicRuntimeSettings.md#barcodeformatids_2) | BarcodeFormat group 2. Read more in [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) |
| [`pdfRasterDPI`](auxiliary-iPublicRuntimeSettings.md#pdfrasterdpi) | Sets the output image resolution. |
| [`scaleDownThreshold`](auxiliary-iPublicRuntimeSettings.md#scaledownthreshold) | Sets the threshold for the image shrinking. |
| [`binarizationModes`](auxiliary-iPublicRuntimeSettings.md#binarizationmodes) | Sets the mode and priority for binarization. |
| [`localizationModes`](auxiliary-iPublicRuntimeSettings.md#localizationmodes) | Sets the mode and priority for localization algorithms. |
| [`furtherModes`](auxiliary-iPublicRuntimeSettings.md#furthermodes) | Further modes settings. Please read more in [`FurtherModes`](auxiliary-iFurtherModes.md) class. |
| [`deblurLevel`](auxiliary-iPublicRuntimeSettings.md#deblurlevel) | Sets the degree of blurriness of the barcode. |
| [`intermediateResultTypes`](auxiliary-iPublicRuntimeSettings.md#intermediateresulttypes) | Sets which types of intermediate result to be kept for further reference. |
| [`intermediateResultSavingMode`](auxiliary-iPublicRuntimeSettings.md#intermediateresultsavingmode) | Sets the mode for saving intermediate result. |
| [`resultCoordinateType`](auxiliary-iPublicRuntimeSettings.md#resultcoordinatetype) | Specifies the format for the coordinates returned. |
| [`textResultOrderModes`](auxiliary-iPublicRuntimeSettings.md#textresultordermodes) | Sets the mode and priority for the order of the text results returned. |
| [`returnBarcodeZoneClarity`](auxiliary-iPublicRuntimeSettings.md#returnbarcodezoneclarity) | Sets whether or not to return the clarity of the barcode zone. |
| [`region`](auxiliary-iPublicRuntimeSettings.md#region) | Sets the scan region. Please read more in [`iRegionDefinition`](auxiliary-iRegionDefinition.md) Class |
| [`minBarcodeTextLength`](auxiliary-iPublicRuntimeSettings.md#minbarcodetextlength) | Sets the range of barcode text length for barcodes search. |
| [`minResultConfidence`](auxiliary-iPublicRuntimeSettings.md#minresultconfidence) | The minimum confidence of the result. |
| [`scaleUpModes`](auxiliary-iPublicRuntimeSettings.md#scaleupmodes) | Sets the mode and priority to control the sampling methods of scale-up for linear barcode with small module sizes. |
| [`pdfReadingMode`](auxiliary-iPublicRuntimeSettings.md#pdfreadingmode) | Sets the way to detect barcodes from a PDF file when using the DecodeFile method. |
| [`deblurModes`](auxiliary-iPublicRuntimeSettings.md#deblurmodes) | Sets the mode and priority for deblurring. |
| [`barcodeZoneMinDistanceToImageBorders`](auxiliary-iPublicRuntimeSettings.md#barcodezonemindistancetoimageborders) | Sets the minimum distance (in pixels) between the barcode zone and image borders. |

## [iFurtherModes](auxiliary-iFurtherModes.md)

`FurtherModes` is an extension of the `PublicRuntimeSettings` class. Through the `FurtherModes`, you can make advanced settings to process the image for barcode reading.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iFurtherModes : NSObject
```
2. 
```swift
class iFurtherModes : NSObject
```

| Attribute | Descriptions |
|---------- | ------------ |
| [`colourClusteringModes`](auxiliary-iFurtherModes.md#colourclusteringmodes) | Sets the mode and priority for colour categorization. |
| [`colourConversionModes`](auxiliary-iFurtherModes.md#colourconversionmodes) | Sets the mode and priority for converting a colour image to a grayscale image. |
| [`grayscaleTransformationModes`](auxiliary-iFurtherModes.md#grayscaletransformationmodes) | Sets the mode and priority for the grayscale image conversion. |
| [`regionPredetectionModes`](auxiliary-iFurtherModes.md#regionpredetectionmodes) | Sets the region pre-detection mode for barcodes search. |
| [`imagePreprocessingModes`](auxiliary-iFurtherModes.md#imagepreprocessingmodes) | Sets the mode and priority for image preprocessing algorithms. |
| [`textureDetectionModes`](auxiliary-iFurtherModes.md#texturedetectionmodes) | Sets the mode and priority for texture detection. |
| [`textFilterModes`](auxiliary-iFurtherModes.md#textfiltermodes) | Sets the mode and priority for text filter. |
| [`dpmCodeReadingModes`](auxiliary-iFurtherModes.md#dpmcodereadingmodes) | Sets the mode and priority for DPM code reading. |
| [`deformationResistingModes`](auxiliary-iFurtherModes.md#deformationresistingmodes) | Sets the mode and priority for deformation resisting. |
| [`barcodeComplementModes`](auxiliary-iFurtherModes.md#barcodecomplementmodes) | Sets the mode and priority to complement the missing parts in the barcode. |
| [`barcodeColourModes`](auxiliary-iFurtherModes.md#barcodecolourmodes) | Sets the mode and priority for the barcode colour mode used to process the barcode zone. |
| [`accompanyingTextRecognitionModes`](auxiliary-iFurtherModes.md#accompanyingtextrecognitionmodes) | Sets the mode and priority to recognize accompanying text. |
