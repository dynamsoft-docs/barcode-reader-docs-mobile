---
layout: default-layout
title: PublicRuntimeSettings Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the PublicRuntimeSettings Class of Dynamsoft Barcode Reader for Android SDK.
keywords: PublicRuntimeSettings, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/android/api-reference/auxiliary-PublicRuntimeSettings-v8.9.0.html
---


# PublicRuntimeSettings

Defines a struct to configure the barcode reading runtime settings. These settings control the barcode recognition process such as which barcode types to decode.

```java
class com.dynamsoft.dbr.PublicRuntimeSettings;
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`terminatePhase`](#terminatephase) | *int* | Sets the phase to stop the barcode reading algorithm. |
| [`timeout`](#timeout) | *int* | Set the maximum time spent on scanning one image (page). |
| [`maxAlgorithmThreadCount`](#maxalgorithmthreadcount) | *int* | Sets the number of threads the image processing algorithm will use to decode barcodes. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* | Sets the number of barcodes expected to be detected for each image. |
| [`barcodeFormatIds`](#barcodeformatids) | *int* | BarcodeFormat group 1. Read more in [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android) |
| [`barcodeFormatIds_2`](#barcodeformatids_2) | *int* | BarcodeFormat group 2. Read more in [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android) |
| [`pdfRasterDPI`](#pdfrasterdpi) | *int* | Sets the output image resolution. |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* | Sets the threshold for the image shrinking. |
| [`binarizationModes`](#binarizationmodes) | *int\[\]* | Sets the mode and priority for binarization. |
| [`localizationModes`](#localizationmodes) | *int\[\]* | Sets the mode and priority for localization algorithms. |
| [`furtherModes`](#furthermodes) | [`FurtherModes`](auxiliary-FurtherModes.html) | Further modes settings. Please read more in [`FurtherModes`](auxiliary-FurtherModes.html) class. |
| [`deblurLevel`](#deblurlevel) | *int* | Sets the degree of blurriness of the barcode. |
| [`intermediateResultTypes`](#intermediateresulttypes) | *int* | Sets which types of intermediate result to be kept for further reference. |
| [`intermediateResultSavingMode`](#intermediateresultsavingmode) | *int* | Sets the mode for saving intermediate result. |
| [`resultCoordinateType`](#resultcoordinatetype) | *int* | Specifies the format for the coordinates returned. |
| [`textResultOrderModes`](#textresultordermodes) | *int\[\]* | Sets the mode and priority for the order of the text results returned. |
| [`returnBarcodeZoneClarity`](#returnbarcodezoneclarity) | *int* | Sets whether or not to return the clarity of the barcode zone. |
| [`region`](#region) | [`RegionDefinition`](auxiliary-FurtherModes.html) | Sets the scan region. Please read more in [`RegionDefinition`](auxiliary-RegionDefinition.html) Class |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *int* | Sets the range of barcode text length for barcodes search. |
| [`minResultConfidence`](#minresultconfidence) | *int* | The minimum confidence of the result. |
| [`scaleUpModes`](#scaleupmodes) | *int\[\]* | Sets the mode and priority to control the sampling methods of scale-up for linear barcode with small module sizes. |
| [`pdfReadingMode`](#pdfreadingmode) | *int* | Sets the way to detect barcodes from a PDF file when using the DecodeFile method. |
| [`deblurModes`](#deblurmodes) | *int\[\]* | Sets the mode and priority for deblurring. |
| [`barcodeZoneMinDistanceToImageBorders`](#barcodezonemindistancetoimageborders) | *int* | Sets the minimum distance (in pixels) between the barcode zone and image borders. |

## terminatePhase

Sets the phase to stop the barcode reading algorithm.

```java
int terminatePhase
```

**Value Range**

Any one of the [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=android) Enumeration items

**Default Value**

`TP_BARCODE_RECOGNIZED`

**Remarks**

When the recognition result is not desired, you can set this parameter can be set to skip certain processing stages.

**See Also**

[`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=android)

## timeout

Sets the maximum amount of time (in milliseconds) that should be spent searching for a barcode per page. It does not include the time taken to load/decode an image (TIFF, PNG, etc.) from disk into memory.

```java
int timeout
```

**Value Range**

[0, 0x7fffffff]

**Default Value**

10000

**Remarks**

If you want to stop reading barcodes after a certain period of time, you can use this parameter to set a timeout.

## maxAlgorithmThreadCount

Sets the number of threads the image processing algorithm will use to decode barcodes.

```java
int timeout
```

**Value Range**

[1, 4]

**Default Value**

4

**Remarks**

To keep a balance between speed and quality, the library concurrently runs four different threads for barcode decoding by default.

## expectedBarcodesCount

Sets the number of barcodes expected to be detected for each image.

```java
int expectedBarcodesCount
```

**Value Range**

[0, 0x7fffffff]

**Default Value**

0

**Remarks**

0: means Unknown and it will find at least one barcode. 1: try to find one barcode. If one barcode is found, the library will stop the localization process and perform barcode decoding. n: try to find n barcodes. If the library only finds m (m<n) barcode, it will try different algorithms till n barcodes are found or all algorithms are tried.

## barcodeFormatIds

Sets the formats of the barcode in BarcodeFormat group 1 to be read. Barcode formats in BarcodeFormat group 1 can be combined.

```java
int barcodeFormatIds
```

**Value Range**

A combined value of [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android) Enumeration items

**Default Value**

`BF_ALL`

**Remarks**

If the barcode type(s) are certain, specifying the barcode type(s) to be read will speed up the recognition process. The barcode format our library will search for is composed of [BarcodeFormat group 1]({{ site.mobile_enum }}barcode-format.html?lang=android) and [BarcodeFormat group 2]({{ site.mobile_enum }}barcode-format2.html?lang=android), so you need to specify the barcode format in group 1 and group 2 individually.

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android), [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android)

## barcodeFormatIds_2

Sets the formats of the barcode in BarcodeFormat group 2 to be read. Barcode formats in BarcodeFormat group 2 can be combined.

```java
int barcodeFormatIds_2
```

**Value Range**

A combined value of [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android) Enumeration items

**Default Value**

`BF2_NULL`

**Remarks**

If the barcode type(s) are certain, specifying the barcode type(s) to be read will speed up the recognition process. The barcode format our library will search for is composed of [BarcodeFormat group 1]({{ site.mobile_enum }}barcode-format.html?lang=android) and [BarcodeFormat group 2]({{ site.mobile_enum }}barcode-format2.html?lang=android), so you need to specify the barcode format in group 1 and group 2 individually.

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android), [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android)

## pdfRasterDPI

Sets the output image resolution.

```java
int pdfRasterDPI
```

**Value Range**

[100, 600]

**Default Value**

300

**Remarks**

When decoding barcodes from a PDF file using the DecodeFile method, the library will convert the PDF file to image(s) first, then perform barcode recognition.

## scaleDownThreshold

Sets the threshold for the image shrinking.

```java
int scaleDownThreshold
```

**Value Range**

[512, 0x7fffffff]

**Default Value**

2300

**Remarks**

If the shorter edge size is larger than the given threshold value, the library will calculate the required height and width of the barcode image and shrink the image to that size before localization. Otherwise, the library will perform barcode localization on the original image.

## binarizationModes

Sets the mode and priority for binarization.

```java
int[] binarizationModes
```

**Value Range**

Each array item can be any one of the [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=android) Enumeration items.

**Default Value**

`[BM_LOCAL_BLOCK,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See Also**

[`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=android)

## localizationModes

Sets the mode and priority for localization algorithms.

```java
int[] localizationModes
```

**Value Range**

Each array item can be any one of the [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=android) Enumeration items.

**Default Value**

`[LM_CONNECTED_BLOCKS, LM_SCAN_DIRECTLY, LM_STATISTICS, LM_LINES, LM_SKIP, LM_SKIP, LM_SKIP, LM_SKIP]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See Also**

[`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=android)  

## furtherModes

Sets further modes.

```java
FurtherModes furtherModes
```

## deblurLevel

Sets the degree of blurriness of the barcode.

```java
int deblurLevel
```

**Value Range**

[0, 9]

**Default Value**

9

**Remarks**

If you have a blurry image, you can set this property to a larger value. The higher the value set, the more effort the library will spend to decode images, but it may also slow down the recognition process.

## intermediateResultTypes

Sets which types of intermediate result to be kept for further reference. Intermediate result types can be combined.

```java
int intermediateResultTypes
```

**Value Range**

A combined value of [`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=android) Enumeration items

**Default Value**

0

**See Also**

[`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=android)

## intermediateResultSavingMode

Sets the mode for saving intermediate result.

```java
int intermediateResultSavingMode
```

**Value Range**

A value of [`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=android) Enumeration items

**Default Value**

IRSM_MEMORY

**See Also**

[`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=android)

## resultCoordinateType

Specifies the format for the coordinates returned.

```java
int resultCoordinateType
```

**Value Range**

Any one of the [`ResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=android) Enumeration items

**Default Value**

IRSM_MEMORY

**See Also**

[`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=android)

## textResultOrderModes

Sets the mode and priority for the order of the text results returned.

```java
int[] textResultOrderModes
```

**Value Range**

Each array item can be any one of the [`EnumTextResultOrderMode`]({{ site.mobile_enum }}text-result-order-mode.html?lang=android) Enumeration items.

**Default Value**

`[TROM_CONFIDENCE, TROM_POSITION, TROM_FORMAT, TROM_SKIP, TROM_SKIP, TROM_SKIP, TROM_SKIP, TROM_SKIP]`

**Remarks**

The array index represents the priority of the item. The smaller the index, the higher the priority.

**See Also**

[`EnumTextResultOrderMode`]({{ site.mobile_enum }}text-result-order-mode.html?lang=android)

## returnBarcodeZoneClarity

Sets whether or not to return the clarity of the barcode zone.

```java
int returnBarcodeZoneClarity
```

**Value Range**

[0,1]

**Default Value**

0

**Remarks**

0: Do not return the clarity of the barcode zone; 1: Return the clarity of the barcode zone.  

## region

Sets the region definition including regionTop, regionLeft, regionRight, regionBottom, and regionMeasuredByPercentage.

```java
RegionDefinition region
```

## minBarcodeTextLength

Sets the range of barcode text length for barcodes search.

```java
int minBarcodeTextLength
```

**Value Range**

[0, 0x7fffffff]

**Default Value**

0

**Remarks**

0: means no limitation on the barcode text length.

## minResultConfidence

The minimum confidence of the result.

```java
int minResultConfidence
```

**Value Range**

[0, 100]

**Default Value**

0

**Remarks**

0: means no limitation on the result confidence.

## scaleUpModes

Sets the mode and priority to control the sampling methods of scale-up for linear barcode with small module sizes.

```java
int[] scaleUpModes[]
```

**Value Range**

Each array item can be any one of the [`EnumScaleUpMode`]({{ site.mobile_enum }}scale-up-mode.html?lang=android) Enumeration items.

**Default Value**

`[SUM_AUTO, SUM_SKIP, SUM_SKIP, SUM_SKIP, SUM_SKIP, SUM_SKIP, SUM_SKIP, SUM_SKIP]`

**Remarks**

The array index represents the priority of the item. The smaller the index, the higher the priority.

**See Also**

[`EnumScaleUpMode`]({{ site.mobile_enum }}scale-up-mode.html?lang=android)

## pdfReadingMode

Sets the way to detect barcodes from a PDF file when using the DecodeFile method.

```java
int pdfReadingMode
```

**Value Range**

Any one of the [`EnumPDFReadingMode`]({{ site.mobile_enum }}pdf-reading-mode.html?lang=android) Enumeration items.

**Default Value**

`PDFRM_AUTO`  

**See Also**

[`EnumPDFReadingMode`]({{ site.mobile_enum }}pdf-reading-mode.html?lang=android)

## deblurModes

Sets the mode and priority for deblurring.

```java
int[] deblurModes
```

**Value Range**

Each array item can be any one of the [`EnumDeblurMode`]({{ site.mobile_enum }}deblur-mode.html?lang=android) Enumeration items.

**Default Value**

`[DM_SKIP, DM_SKIP, DM_SKIP, DM_SKIP, DM_SKIP, DM_SKIP, DM_SKIP, DM_SKIP, DM_SKIP, DM_SKIP]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See Also**

    [`EnumDeblurMode`]({{ site.mobile_enum }}deblur-mode.html?lang=android)

## barcodeZoneMinDistanceToImageBorders

Sets the minimum distance (in pixels) between the barcode zone and image borders.

```java
int barcodeZoneMinDistanceToImageBorders
```

**Value Range**

[0, 0x7fffffff]

**Default Value**

0

**Remarks**

0: means no limitation on the distance.
