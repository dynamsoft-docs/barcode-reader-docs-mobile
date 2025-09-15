---
layout: default-layout
title: IntermediateResult index - Dynamsoft Barcode Reader Android API Reference
description: This page shows the IntermediateResult index of Dynamsoft Barcode Reader for Android SDK.
keywords: IntermediateResult, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: False
noTitleIndex: true
ignore: true
---

# Intermediate Result Classes

## [IntermediateResult](auxiliary-IntermediateResult.html)

`IntermediateResult` is the class that stores the intermediate result data.

```java
class com.dynamsoft.dbr.IntermediateResult;
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`results`](auxiliary-IntermediateResult.html#results) | *Object\[\]* | One of the following types: Array of [`Contour`](auxiliary-Contour.html), Array of [`ImageData`](auxiliary-ImageData.html), Array of [`LineSegment`](auxiliary-LineSegment.html), Array of [`LocalizationResult`](auxiliary-LocalizationResult.html), Array of [`RegionOfInterest`](auxiliary-RegionOfInterest.html). |
| [`dataType`](auxiliary-IntermediateResult.html#datatype) | *int* | The data type of the intermediate result. |
| [`resultType`](auxiliary-IntermediateResult.html#resulttype) | *int* | Intermediate result type. |
| [`barcodeComplementMode`](auxiliary-IntermediateResult.html#barcodecomplementmode) | *int* | The [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=android) used when generating the current intermediate result. |
| [`bcmIndex`](auxiliary-IntermediateResult.html#bcmindex) | *int* | The array index of current used [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=android) in the [`barcodeComplementModes`](auxiliary-FurtherModes.html#barcodecomplementmodes) setting. |
| [`deformationResistingMode`](auxiliary-IntermediateResult.html#deformationresistingmode) | *int* | The [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=android) used when generating the current intermediate result. |
| [`drmIndex`](auxiliary-IntermediateResult.html#drmindex) | *int* | The array index of current used [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=android) in the [`deformationResistingModes`](auxiliary-FurtherModes.html#deformationresistingmodes) setting. |
| [`dpmCodeReadingMode`](auxiliary-IntermediateResult.html#dpmcodereadingmode) | *int* | The [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=android) used when generating the current intermediate result. |
| [`dpmcrmIndex`](auxiliary-IntermediateResult.html#dpmcrmindex) | *int* | The array index of current used [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=android) in the [`dpmCodeReadingModes`](auxiliary-FurtherModes.html#dpmcodereadingmodes) setting. |
| [`rotationMatrix`](auxiliary-IntermediateResult.html#rotationmatrix) | *double\[\]* | The rotation matrix. |
| [`textFilterMode`](auxiliary-IntermediateResult.html#textfiltermode) | *int* | The [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=android) used when generating the current intermediate result. |
| [`tfmIndex`](auxiliary-IntermediateResult.html#tfmindex) | *int* | The array index of current used [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=android) in the [`textFilterModes`](auxiliary-FurtherModes.html#textfiltermodes) setting. |
| [`localizationMode`](auxiliary-IntermediateResult.html#localizationmode) | *int* | The [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=android) used when generating the current intermediate result. |
| [`lmIndex`](auxiliary-IntermediateResult.html#lmindex) | *int* | The array index of current used [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=android) in the [`localizationModes`](auxiliary-PublicRuntimeSettings.html#localizationmodes) setting. |
| [`binarizationMode`](auxiliary-IntermediateResult.html#binarizationmode) | *int* | The [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=android) used when generating the current intermediate result. |
| [`bmIndex`](auxiliary-IntermediateResult.html#bmindex) | *int* | The array index of current used [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=android) in the [`binarizationModes`](auxiliary-PublicRuntimeSettings.html#binarizationmodes) setting. |
| [`imagePreprocessingMode`](auxiliary-IntermediateResult.html#imagepreprocessingmode) | *int* | The [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=android) used when generating the current intermediate result. |
| [`ipmIndex`](auxiliary-IntermediateResult.html#ipmindex) | *int* | The array index of current used [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=android) in [`imagePreprocessingModes`](auxiliary-FurtherModes.html#imagepreprocessingmodes) setting. |
| [`roiId`](auxiliary-IntermediateResult.html#roiid) | *int* | The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image. |
| [`regionPredetectionMode`](auxiliary-IntermediateResult.html#regionpredetectionmode) | *int* | The [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=android) used when generating the current intermediate result. |
| [`rpmIndex`](auxiliary-IntermediateResult.html#rpmindex) | *int* | The array index of current used [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=android) in the [`regionPredetectionModes`](auxiliary-FurtherModes.html#regionpredetectionmodes) setting. |
| [`grayscaleTransformationMode`](auxiliary-IntermediateResult.html#grayscaletransformationmode) | *int* | The [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=android) used when generating the current intermediate result. |
| [`gtmIndex`](auxiliary-IntermediateResult.html#gtmindex) | *int* | The array index of current used [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=android) in the [`grayscaleTransformationModes`](auxiliary-FurtherModes.html#grayscaletransformationmodes) setting. |
| [`colourConversionMode`](auxiliary-IntermediateResult.html#colourconversionmode) | *int* | The [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=android) used when generating the current intermediate result. |
| [`cicmIndex`](auxiliary-IntermediateResult.html#cicmindex) | *int* | The array index of current used [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=android) in the [`colourConversionModes`](auxiliary-FurtherModes.html#colourconversionmodes) setting. |
| [`colourClusteringMode`](auxiliary-IntermediateResult.html#colourclusteringmode) | *int* | The [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=android) used when generating the current intermediate result. |
| [`ccmIndex`](auxiliary-IntermediateResult.html#ccmindex) | *int* | The array index of current used [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=android) in the [`colourClusteringModes`](auxiliary-FurtherModes.html#colourclusteringmodes) setting. |
| [`scaleDownRatio`](auxiliary-IntermediateResult.html#scaledownratio) | *int* | The scale down ratio. |
| [`frameId`](auxiliary-IntermediateResult.html#frameid) | *int* | The ID of the operated frame. |
| [`rpmColourArgumentIndex`](auxiliary-IntermediateResult.html#rpmcolourargumentindex) | *int* | The index of the rpm colour argument. |

**Code Snippet**

```java
barcodeReader.initIntermediateResults(EnumIntermediateResultType.IRT_ORIGINAL_IMAGE);
IntermediateResult[] intermediateResults = barcodeReader.getIntermediateResults();
```

## [Contour](auxiliary-Contour.html)

`contour` is one of the [`results`](auxiliary-IntermediateResult.html#results) type in `IntermediateResult`.

```java
class com.dynamsoft.dbr.Contour;
```

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`points`](auxiliary-Contour.html#points) | *Point\[\]* | The array of the points that surround the barcode area. |

**Code Snippet**

```java
Contour[] contours = (Contour[]) intermediateResults[i].results;
```

## [ImageData](auxiliary-ImageData.html)

`ImageData` is one of the [`results`](auxiliary-IntermediateResult.html#results) type in `IntermediateResult`.

```java
class com.dynamsoft.dbr.ImageData;
```

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`bytes`](auxiliary-ImageData.html#bytes) | *byte\[\]* | The image data content in a byte array. |
| [`width`](auxiliary-ImageData.html#width) | *int* | The width of the image in pixels. |
| [`height`](auxiliary-ImageData.html#height) | *int* | The height of the image in pixels. |
| [`stride`](auxiliary-ImageData.html#stride) | *int* | The stride (or scan width) of the image. |
| [`format`](auxiliary-ImageData.html#format) | *int* | The image pixel format used in the image byte array. |

**Code Snippet**

```java
ImageData[] imageData = (ImageData[]) intermediateResults[i].results;
```

## [LineSegment](auxiliary-LineSegment.html)

`LineSegment` is one of the [`results`](auxiliary-IntermediateResult.html#results) type in `IntermediateResult`.

```java
class com.dynamsoft.dbr.LineSegment;
```

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`startPoint`](auxiliary-LineSegment.html#startpoint) | [`Point`](auxiliary-Point.html) | The start point of the line segment. |
| [`endPoint`](auxiliary-LineSegment.html#endpoint) | [`Point`](auxiliary-Point.html) | The end point of the line segment. |
| [`linesConfidenceCoefficients`](auxiliary-LineSegment.html#linesconfidencecoefficients) | *byte\[\]* | The confidence coefficients for lines. |

**Code Snippet**

```java
LineSegment[] lineSegment = (LineSegment[]) intermediateResults[i].results;
```

## [RegionOfInterest](auxiliary-RegionOfInterest.html)

`RegionOfInterest` is one of the [`results`](auxiliary-IntermediateResult.html#results) type in `IntermediateResult`.

```java
class com.dynamsoft.dbr.RegionOfInterest;
```

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`roiId`](auxiliary-RegionOfInterest.html#roiid) | *int* | The ID generated by the SDK. |
| [`point`](auxiliary-RegionOfInterest.html#point) | [`Point`](auxiliary-Point.html) | The left top point of the region. |
| [`width`](auxiliary-RegionOfInterest.html#width) | *int* | The width of the region. |
| [`height`](auxiliary-RegionOfInterest.html#height) | *int* | The height of the region. |

**Code Snippet**

```java
RegionOfInterest[] regionOfInterest = (RegionOfInterest[]) intermediateResults[i].results;
```

## LocalizationResult

View more in [TextResult >> LocalizationResult](auxiliary-LocalizationResult.html)

```java
class com.dynamsoft.dbr.LocalizationResult;
```

`LocalizationResult` can be the extension of class [`TextResult`](auxiliary-TextResult.html) and class [`IntermediateResult`](auxiliary-IntermediateResult.html). It stores the localization result information.

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`terminatePhase`](auxiliary-LocalizationResult.html#terminatephase) | *int* | The terminate phase of localization result. |
| [`barcodeFormat`](auxiliary-LocalizationResult.html#barcodeformat) | *int* | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](auxiliary-LocalizationResult.html#barcodeformatstring) | *String* | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](auxiliary-LocalizationResult.html#barcodeformat_2) | *int* | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](auxiliary-LocalizationResult.html#barcodeformatstring_2) | *String* | Barcode type in BarcodeFormat group 2 as string. |
| [`resultPoints`](auxiliary-LocalizationResult.html#resultpoints) | [`Point`](auxiliary-Point.html)\[\] | The vertices coordinates information of the barcode region. |
| [`angle`](auxiliary-LocalizationResult.html#angle) | *int* | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](auxiliary-LocalizationResult.html#modulesize) | *int* | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](auxiliary-LocalizationResult.html#pagenumber) | *int* | The page number the barcode located in. The index is 0-based. |
| [`regionName`](auxiliary-LocalizationResult.html#regionname) | *String* | The region name the barcode located in. |
| [`documentName`](auxiliary-LocalizationResult.html#documentname) | *String* | The document name. |
| [`resultCoordinateType`](auxiliary-LocalizationResult.html#resultcoordinatetype) | *int* | The coordinate type. |
| [`accompanyingTextBytes`](auxiliary-LocalizationResult.html#accompanyingtextbytes) | *byte\[\]* | The accompanying text content in a byte array. |
| [`confidence`](auxiliary-LocalizationResult.html#confidence) | *int* | The confidence of the localization result. |

**Code Snippet**

```java
LocalizationResult[] localizationResult = (LocalizationResult[]) intermediateResults[i].results;
```
