---
layout: default-layout
title: Parameter Configurations - Dynamsoft Barcode Reader Android API Reference
description: This page shows the Parameter Configurations of Dynamsoft Barcode Reader for Android SDK.
keywords: Parameter Configurations, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
ignore: true
permalink: /programming/android/api-reference/auxiliary-parameter-index.html
---

# Parameter Configuration Classes

## [PublicRuntimeSettings](auxiliary-PublicRuntimeSettings.html)

You can update most of the parameter settings through the `PublicRuntimeSettings` class.

```java
class com.dynamsoft.dbr.PublicRuntimeSettings;
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`terminatePhase`](auxiliary-PublicRuntimeSettings.html#terminatephase) | *int* | Sets the phase to stop the barcode reading algorithm. |
| [`timeout`](auxiliary-PublicRuntimeSettings.html#timeout) | *int* | Set the maximum time spent on scanning one image (page). |
| [`maxAlgorithmThreadCount`](auxiliary-PublicRuntimeSettings.html#maxalgorithmthreadcount) | *int* | Sets the number of threads the image processing algorithm will use to decode barcodes. |
| [`expectedBarcodesCount`](auxiliary-PublicRuntimeSettings.html#expectedbarcodescount) | *int* | Sets the number of barcodes expected to be detected for each image. |
| [`barcodeFormatIds`](auxiliary-PublicRuntimeSettings.html#barcodeformatids) | *int* | BarcodeFormat group 1. Read more in [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android) |
| [`barcodeFormatIds_2`](auxiliary-PublicRuntimeSettings.html#barcodeformatids_2) | *int* | BarcodeFormat group 2. Read more in [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android) |
| [`pdfRasterDPI`](auxiliary-PublicRuntimeSettings.html#pdfrasterdpi) | *int* | Sets the output image resolution. |
| [`scaleDownThreshold`](auxiliary-PublicRuntimeSettings.html#scaledownthreshold) | *int* | Sets the threshold for the image shrinking. |
| [`binarizationModes`](auxiliary-PublicRuntimeSettings.html#binarizationmodes) | *int\[\]* | Sets the mode and priority for binarization. |
| [`localizationModes`](auxiliary-PublicRuntimeSettings.html#localizationmodes) | *int\[\]* | Sets the mode and priority for localization algorithms. |
| [`furtherModes`](auxiliary-PublicRuntimeSettings.html#furthermodes) | [`FurtherModes`](auxiliary-FurtherModes.html) | Further modes settings. Please read more in [`FurtherModes`](auxiliary-FurtherModes.html) class. |
| [`deblurLevel`](auxiliary-PublicRuntimeSettings.html#deblurlevel) | *int* | Sets the degree of blurriness of the barcode. |
| [`intermediateResultTypes`](auxiliary-PublicRuntimeSettings.html#intermediateresulttypes) | *int* | Sets which types of intermediate result to be kept for further reference. |
| [`intermediateResultSavingMode`](auxiliary-PublicRuntimeSettings.html#intermediateresultsavingmode) | *int* | Sets the mode for saving intermediate result. |
| [`resultCoordinateType`](auxiliary-PublicRuntimeSettings.html#resultcoordinatetype) | *int* | Specifies the format for the coordinates returned. |
| [`textResultOrderModes`](auxiliary-PublicRuntimeSettings.html#textresultordermodes) | *int\[\]* | Sets the mode and priority for the order of the text results returned. |
| [`returnBarcodeZoneClarity`](auxiliary-PublicRuntimeSettings.html#returnbarcodezoneclarity) | *int* | Sets whether or not to return the clarity of the barcode zone. |
| [`region`](auxiliary-PublicRuntimeSettings.html#region) | [`RegionDefinition`](auxiliary-FurtherModes.html) | Sets the scan region. Please read more in [`RegionDefinition`](auxiliary-RegionDefinition.html) Class |
| [`minBarcodeTextLength`](auxiliary-PublicRuntimeSettings.html#minbarcodetextlength) | *int* | Sets the range of barcode text length for barcodes search. |
| [`minResultConfidence`](auxiliary-PublicRuntimeSettings.html#minresultconfidence) | *int* | The minimum confidence of the result. |
| [`scaleUpModes`](auxiliary-PublicRuntimeSettings.html#scaleupmodes) | *int\[\]* | Sets the mode and priority to control the sampling methods of scale-up for linear barcode with small module sizes. |
| [`pdfReadingMode`](auxiliary-PublicRuntimeSettings.html#pdfreadingmode) | *int* | Sets the way to detect barcodes from a PDF file when using the DecodeFile method. |
| [`deblurModes`](auxiliary-PublicRuntimeSettings.html#deblurmodes) | *int\[\]* | Sets the mode and priority for deblurring. |
| [`barcodeZoneMinDistanceToImageBorders`](auxiliary-PublicRuntimeSettings.html#barcodezonemindistancetoimageborders) | *int* | Sets the minimum distance (in pixels) between the barcode zone and image borders. |

**Code Snippet**

```java
PublicRuntimeSettings runtimeSettings = barcodeReader.getRuntimeSettings();
// Make some settings here
// runtimeSettings.****** = ******
barcodeReader.updateRuntimeSettings(runtimeSettings);
```

## [FurtherModes](auxiliary-FurtherModes.html)

`FurtherModes` is an extension of the `PublicRuntimeSettings` class. Through the `FurtherModes`, you can make advanced settings to process the image for barcode reading.

```java
class com.dynamsoft.dbr.FurtherModes;
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----- |
| [`colourClusteringModes`](auxiliary-FurtherModes.html#colourclusteringmodes) | *int\[\]* | Sets the mode and priority for colour categorization. |
| [`colourConversionModes`](auxiliary-FurtherModes.html#colourconversionmodes) | *int\[\]* | Sets the mode and priority for converting a colour image to a grayscale image. |
| [`grayscaleTransformationModes`](auxiliary-FurtherModes.html#grayscaletransformationmodes) | *int\[\]* | Sets the mode and priority for the grayscale image conversion. |
| [`regionPredetectionModes`](auxiliary-FurtherModes.html#regionpredetectionmodes) | *int\[\]* | Sets the region pre-detection mode for barcodes search. |
| [`imagePreprocessingModes`](auxiliary-FurtherModes.html#imagepreprocessingmodes) | *int\[\]* | Sets the mode and priority for image preprocessing algorithms. |
| [`textureDetectionModes`](auxiliary-FurtherModes.html#texturedetectionmodes) | *int\[\]* | Sets the mode and priority for texture detection. |
| [`textFilterModes`](auxiliary-FurtherModes.html#textfiltermodes) | *int\[\]* | Sets the mode and priority for text filter. |
| [`textAssistedCorrectionMode`](auxiliary-FurtherModes.html#textassistedcorrectionmode) | *int* | Sets the mode of text assisted correction for barcode decoding. |
| [`dpmCodeReadingModes`](auxiliary-FurtherModes.html#dpmcodereadingmodes) | *int\[\]* | Sets the mode and priority for DPM code reading. |
| [`deformationResistingModes`](auxiliary-FurtherModes.html#deformationresistingmodes) | *int\[\]* | Sets the mode and priority for deformation resisting. |
| [`barcodeComplementModes`](auxiliary-FurtherModes.html#barcodecomplementmodes) | *int\[\]* | Sets the mode and priority to complement the missing parts in the barcode. |
| [`barcodeColourModes`](auxiliary-FurtherModes.html#barcodecolourmodes) | *int\[\]* | Sets the mode and priority for the barcode colour mode used to process the barcode zone. |
| [`accompanyingTextRecognitionModes`](auxiliary-FurtherModes.html#accompanyingtextrecognitionmodes) | *int\[\]* | Sets the mode and priority to recognize accompanying text. |

**Code Snippet**

```java
FurtherModes furtherModes = runtimeSettings.furtherModes;
```
