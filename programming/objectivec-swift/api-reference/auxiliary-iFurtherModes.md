---
layout: default-layout
title: iFurtherModes Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iFurtherModes Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iFurtherModes, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iFurtherModes.html
---


# Class iFurtherModes

Stores the FurtherModes.

```objc
@interface iFurtherModes
```  

| Attribute | Type | Descriptions |
|---------- | ---- | ----- |
| [`colourClusteringModes`](auxiliary-iFurtherModes.md#colourclusteringmodes) | *NSArray*\* | Sets the mode and priority for colour categorization. |
| [`colourConversionModes`](auxiliary-iFurtherModes.md#colourconversionmodes) | *NSArray*\* | Sets the mode and priority for converting a colour image to a grayscale image. |
| [`grayscaleTransformationModes`](auxiliary-iFurtherModes.md#grayscaletransformationmodes) | *NSArray*\* | Sets the mode and priority for the grayscale image conversion. |
| [`regionPredetectionModes`](auxiliary-iFurtherModes.md#regionpredetectionmodes) | *NSArray*\* | Sets the region pre-detection mode for barcodes search. |
| [`imagePreprocessingModes`](auxiliary-iFurtherModes.md#imagepreprocessingmodes) | *NSArray*\* | Sets the mode and priority for image preprocessing algorithms. |
| [`textureDetectionModes`](auxiliary-iFurtherModes.md#texturedetectionmodes) | *NSArray*\* | Sets the mode and priority for texture detection. |
| [`textFilterModes`](auxiliary-iFurtherModes.md#textfiltermodes) | *NSArray*\* | Sets the mode and priority for text filter. |
| [`dpmCodeReadingModes`](auxiliary-iFurtherModes.md#dpmcodereadingmodes) | *NSArray*\* | Sets the mode and priority for DPM code reading. |
| [`deformationResistingModes`](auxiliary-iFurtherModes.md#deformationresistingmodes) | *NSArray*\* | Sets the mode and priority for deformation resisting. |
| [`barcodeComplementModes`](auxiliary-iFurtherModes.md#barcodecomplementmodes) | *NSArray*\* | Sets the mode and priority to complement the missing parts in the barcode. |
| [`barcodeColourModes`](auxiliary-iFurtherModes.md#barcodecolourmodes) | *NSArray*\* | Sets the mode and priority for the barcode colour mode used to process the barcode zone. |
| [`accompanyingTextRecognitionModes`](auxiliary-iFurtherModes.md#accompanyingtextrecognitionmodes) | *NSArray*\* | Sets the mode and priority to recognize accompanying text. |

## colourClusteringModes

Sets the mode and priority for colour categorization. Not supported yet.  

```objc
@property (nonatomic, readwrite, nullable) NSArray* colourClusteringModes
```

**Value Range**

Each array item can be any one of the [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) Enumeration items.  

**Default Value**

`[EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See Also**

[`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift)

## colourConversionModes

Sets the mode and priority for converting a colour image to a grayscale image.

```objc
@property (nonatomic, readwrite, nullable) NSArray* colourConversionModes
```

**Value Range**

Each array item can be any one of the [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) Enumeration items.

**Default Value**

`[EnumColourConversionModeGeneral, EnumColourConversionModeSkip, EnumColourConversionModeSkip, EnumColourConversionModeSkip, EnumColourConversionModeSkip, EnumColourConversionModeSkip, EnumColourConversionModeSkip, EnumColourConversionModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See Also**

[`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift)

## grayscaleTransformationModes

Sets the mode and priority for the grayscale image conversion.

```objc
@property (nonatomic, readwrite, nullable) NSArray* grayscaleTransformationModes
```

**Value Range**

Each array item can be any one of the [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) Enumeration items.

**Default Value**

`[EnumGrayscaleTransformationModeOriginal, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See Also**

[`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift)

## regionPredetectionModes

Sets the region pre-detection mode for barcodes search.

```objc
@property (nonatomic, readwrite, nullable) NSArray* regionPredetectionModes
```

**Value Range**

Each array item can be any one of the [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) Enumeration items.  

**Default Value**

`[EnumRegionPredetectionModeGeneral, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is. If the image is large and the barcode on the image is very small, it is recommended to enable region predetection to speed up the localization process and recognition accuracy.

**See Also**

[`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift)

## imagePreprocessingModes

Sets the mode and priority for image preprocessing algorithms.

```objc
@property (nonatomic, readwrite, nullable) NSArray* imagePreprocessingModes
```

**Value Range**

Each array item can be any one of the [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) Enumeration items.  

**Default Value**

`[EnumImagePreprocessingModeGeneral, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See Also**

[`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift)

## textureDetectionModes

Sets the mode and priority for texture detection.

```objc
@property (nonatomic, readwrite, nullable) NSArray* textureDetectionModes
```

**Value Range**

Each array item can be any one of the [`EnumTextureDetectionMode`]({{ site.mobile_enum }}texture-detection-mode.html?lang=objc,swift) Enumeration items.  

**Default Value**

`[EnumTextureDetectionModeGeneralWidthConcentration, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See Also**

[`EnumTextureDetectionMode`]({{ site.mobile_enum }}texture-detection-mode.html?lang=objc,swift)

## textFilterModes

Sets the mode and priority for text filter.

```objc
@property (nonatomic, readwrite, nullable) NSArray* textFilterModes
```

**Value Range**

Each array item can be any one of the [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) Enumeration items.  

**Default Value**

`[EnumTextFilterModeGeneralContour, EnumTextFilterModeSkip, EnumTextFilterModeSkip, EnumTextFilterModeSkip, EnumTextFilterModeSkip, EnumTextFilterModeSkip, EnumTextFilterModeSkip, EnumTextFilterModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is. If the image contains a lot of text, you can enable text filter to speed up the localization process.

**See Also**

[`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift)

## dpmCodeReadingModes

Sets the mode and priority for DPM code reading.

```objc
@property (nonatomic, readwrite, nullable) NSArray* dpmCodeReadingModes
```

**Value Range**

Each array item can be any one of the [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) Enumeration items.  

**Default Value**

`[EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See Also**

[`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift)

## deformationResistingModes

Sets the mode and priority for deformation resisting.

```objc
@property (nonatomic, readwrite, nullable) NSArray* deformationResistingModes
```

**Value Range**

Each array item can be any one of the [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) Enumeration items.  

**Default Value**

`[EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See Also**

[`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift)

## barcodeComplementModes

Sets the mode and priority to complement the missing parts in the barcode.

```objc
@property (nonatomic, readwrite, nullable) NSArray* barcodeComplementModes
```

**Value Range**

Each array item can be any one of the [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) Enumeration items.  

**Default Value**

`[EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See Also**

[`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift)

## barcodeColourModes

Sets the mode and priority for the barcode colour mode used to process the barcode zone.

```objc
@property (nonatomic, readwrite, nullable) NSArray* barcodeColourModes
```

**Value Range**

Each array item can be any one of the [`EnumBarcodeColourMode`]({{ site.mobile_enum }}barcode-colour-mode.html?lang=objc,swift) Enumeration items.  

**Default Value**

`[EnumBarcodeColourModeDarkOnLight, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See Also**

[`EnumBarcodeColourMode`]({{ site.mobile_enum }}barcode-colour-mode.html?lang=objc,swift)
