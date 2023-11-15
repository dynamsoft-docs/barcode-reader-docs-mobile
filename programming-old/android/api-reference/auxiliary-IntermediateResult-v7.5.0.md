---
layout: default-layout
title: IntermediateResult Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the IntermediateResult Class of Dynamsoft Barcode Reader for Android SDK.
keywords: IntermediateResult, class, api reference, android
needAutoGenerateSidebar: true
permalink: /programming/android/api-reference/auxiliary-IntermediateResult-v7.5.0.html
---


# IntermediateResult

Stores the intermediate result.

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`results`](#results) | *Object\[\]* |
| [`dataType`](#datatype) | *int* |
| [`resultType`](#resulttype) | *int* |
| [`barcodeComplementMode`](#barcodecomplementmode) | *int* |
| [`bcmIndex`](#bcmindex) | *int* |
| [`deformationResistingMode`](#deformationresistingmode) | *int* |
| [`drmIndex`](#drmindex) | *int* |
| [`dpmCodeReadingMode`](#dpmcodereadingmode) | *int* |
| [`dpmcrmIndex`](#dpmcrmindex) | *int* |
| [`rotationMatrix`](#rotationmatrix) | *double\[\]* |
| [`textFilterMode`](#textfiltermode) | *int* |
| [`tfmIndex`](#tfmindex) | *int* |
| [`localizationMode`](#localizationmode) | *int* |
| [`lmIndex`](#lmindex) | *int* |
| [`binarizationMode`](#binarizationmode) | *int* |
| [`bmIndex`](#bmindex) | *int* |
| [`imagePreprocessingMode`](#imagepreprocessingmode) | *int* |
| [`ipmIndex`](#ipmindex) | *int* |
| [`roiId`](#roiid) | *int* |
| [`regionPredetectionMode`](#regionpredetectionmode) | *int* |
| [`rpmIndex`](#rpmindex) | *int* |
| [`grayscaleTransformationMode`](#grayscaletransformationmode) | *int* |
| [`gtmIndex`](#gtmindex) | *int* |
| [`colourConversionMode`](#colourconversionmode) | *int* |
| [`cicmIndex`](#cicmindex) | *int* |
| [`colourClusteringMode`](#colourclusteringmode) | *int* |
| [`ccmIndex`](#ccmindex) | *int* |
| [`scaleDownRatio`](#scaledownratio) | *int* |
| [`frameId`](#frameid) | *int* |

### results

One of the following types: Array of [`Contour`](auxiliary-Contour.html), Array of [`ImageData`](auxiliary-ImageData.html), Array of [`LineSegment`](auxiliary-LineSegment.html), Array of [`LocalizationResult`](auxiliary-LocalizationResult.html), Array of [`RegionOfInterest`](auxiliary-RegionOfInterest.html).

```java
Object[] com.dynamsoft.barcode.IntermediateResult.results
```

### dataType

The data type of the intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.dataType
```

### resultType

Intermediate result type.

```java
int com.dynamsoft.barcode.IntermediateResult.resultType
```

### barcodeComplementMode

The [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=android) used when generating the current intermediate result.

```java
iny com.dynamsoft.barcode.IntermediateResult.barcodeComplementMode
```

### bcmIndex

The array index of current used [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=android) in the [`barcodeComplementModes`](auxiliary-FurtherModes.html#barcodecomplementmodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.bcmIndex
```

### deformationResistingMode

The [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=android) used when generating the current intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.deformationResistingMode
```

### drmIndex

The array index of current used [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=android) in the [`deformationResistingModes`](auxiliary-FurtherModes.html#deformationresistingmodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.drmIndex
```

### dpmCodeReadingMode

The [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=android) used when generating the current intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.dpmCodeReadingMode
```

### dpmcrmIndex

The array index of current used [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=android) in the [`dpmCodeReadingModes`](auxiliary-FurtherModes.html#dpmcodereadingmodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.dpmcrmIndex
```

### rotationMatrix

The rotation matrix.

```java
double[] com.dynamsoft.barcode.IntermediateResult.rotationMatrix
```

### textFilterMode

The [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=android) used when generating the current intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.textFilterMode
```

### tfmIndex

The array index of current used [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=android) in the [`textFilterModes`](auxiliary-FurtherModes.html#textfiltermodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.tfmIndex
```

### localizationMode

The [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=android) used when generating the current intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.localizationMode
```

### lmIndex

The array index of current used [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=android) in the [`localizationModes`](auxiliary-PublicRuntimeSettings.html#localizationmodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.lmIndex
```

### binarizationMode

The [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=android) used when generating the current intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.binarizationMode
```

### bmIndex

The array index of current used [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=android) in the [`binarizationModes`](auxiliary-PublicRuntimeSettings.html#binarizationmodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.bmIndex
```

### imagePreprocessingMode

The [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=android) used when generating the current intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.imagePreprocessingMode
```

### ipmIndex

The array index of current used [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=android) in [`imagePreprocessingModes`](auxiliary-FurtherModes.html#imagepreprocessingmodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.ipmIndex
```

### roiId

The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image.

```java
int com.dynamsoft.barcode.IntermediateResult.roiId
```

### regionPredetectionMode

The [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=android) used when generating the current intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.regionPredetectionMode
```

### rpmIndex

The array index of current used [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=android) in the [`regionPredetectionModes`](auxiliary-FurtherModes.html#regionpredetectionmodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.rpmIndex
```

### grayscaleTransformationMode

The [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=android) used when generating the current intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.grayscaleTransformationMode
```

### gtmIndex

The array index of current used [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=android) in the [`grayscaleTransformationModes`](auxiliary-FurtherModes.html#grayscaletransformationmodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.gtmIndex
```

### colourConversionMode

The [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=android) used when generating the current intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.colourConversionMode
```

### cicmIndex

The array index of current used [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=android) in the [`colourConversionModes`](auxiliary-FurtherModes.html#colourconversionmodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.cicmIndex
```

### colourClusteringMode

The [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=android) used when generating the current intermediate result.

```java
int com.dynamsoft.barcode.IntermediateResult.colourClusteringMode
```

### ccmIndex

The array index of current used [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=android) in the [`colourClusteringModes`](auxiliary-FurtherModes.html#colourclusteringmodes) setting.

```java
int com.dynamsoft.barcode.IntermediateResult.ccmIndex
```

### scaleDownRatio

The scale down ratio.

```java
int com.dynamsoft.barcode.IntermediateResult.scaleDownRatio
```

### frameId

The ID of the operated frame.

```java
int com.dynamsoft.barcode.IntermediateResult.frameId
```
