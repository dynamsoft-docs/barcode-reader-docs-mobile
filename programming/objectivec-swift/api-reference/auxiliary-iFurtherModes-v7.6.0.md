---
layout: default-layout
title: iFurtherModes Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iFurtherModes Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iFurtherModes, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iFurtherModes-v7.6.0.html
---


# iFurtherModes

Stores the FurtherModes.

## Typedefs

```objc
@interface iFurtherModes
```  
  
---

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`colourClusteringModes`](#colourclusteringmodes) | *NSArray*\* |
| [`colourConversionModes`](#colourconversionmodes) | *NSArray*\* |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *NSArray*\* |
| [`regionPredetectionModes`](#regionpredetectionmodes) | *NSArray*\* |
| [`imagePreprocessingModes`](#imagepreprocessingmodes) | *NSArray*\* |
| [`textureDetectionModes`](#texturedetectionmodes) | *NSArray*\* |
| [`textFilterModes`](#textfiltermodes) | *NSArray*\* |
| [`textAssistedCorrectionMode`](#textassistedcorrectionmode) | `EnumTextAssistedCorrectionMode` |
| [`dpmCodeReadingModes`](#dpmcodereadingmodes) | *NSArray*\* |
| [`deformationResistingModes`](#deformationresistingmodes) | *NSArray*\* |
| [`barcodeComplementModes`](#barcodecomplementmodes) | *NSArray*\* |
| [`barcodeColourModes`](#barcodecolourmodes) | *NSArray*\* |
| [`accompanyingTextRecognitionModes`](#accompanyingtextrecognitionmodes) | *NSArray*\* |

### colourClusteringModes

Sets the mode and priority for colour categorization. Not supported yet.  

```objc
NSArray* colourClusteringModes[8]
```

**Value range**

Each array item can be any one of the [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift) Enumeration items.  

**Default value**

`[EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip, EnumColourClusteringModeSkip]`  

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See also**
   [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=objc,swift)

### colourConversionModes

Sets the mode and priority for converting a colour image to a grayscale image.

```objc
NSArray* colourConversionModes[8]
```

**Value range**

Each array item can be any one of the [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift) Enumeration items.

**Default value**

` [EnumColourConversionModeGeneral, EnumColourConversionModeSkip, EnumColourConversionModeSkip, EnumColourConversionModeSkip, EnumColourConversionModeSkip, EnumColourConversionModeSkip, EnumColourConversionModeSkip, EnumColourConversionModeSkip]`

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**

[`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=objc,swift)

### grayscaleTransformationModes

Sets the mode and priority for the grayscale image conversion.

```objc
NSArray* grayscaleTransformationModes[8]
```

**Value range**

Each array item can be any one of the [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift) Enumeration items.

**Default value**

`[EnumGrayscaleTransformationModeOriginal, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip, EnumGrayscaleTransformationModeSkip]`  

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**
   [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=objc,swift)

### regionPredetectionModes

Sets the region pre-detection mode for barcodes search.

```objc
NSArray* regionPredetectionModes[8]
```

**Value range**

Each array item can be any one of the [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift) Enumeration items.  

**Default value**

`[EnumRegionPredetectionModeGeneral, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip, EnumRegionPredetectionModeSkip]`

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is. If the image is large and the barcode on the image is very small, it is recommended to enable region predetection to speed up the localization process and recognition accuracy.

**See also**

[`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=objc,swift)

### imagePreprocessingModes

Sets the mode and priority for image preprocessing algorithms.

```objc
NSArray* imagePreprocessingModes[8]
```

**Value range**

Each array item can be any one of the [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift) Enumeration items.  

**Default value**

` [EnumImagePreprocessingModeGeneral, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip, EnumImagePreprocessingModeSkip]`

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See also**
   [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=objc,swift)

### textureDetectionModes

Sets the mode and priority for texture detection.

```objc
NSArray* textureDetectionModes[8]
```

**Value range**

Each array item can be any one of the [`EnumTextureDetectionMode`]({{ site.mobile_enum }}texture-detection-mode.html?lang=objc,swift) Enumeration items.  

**Default value**

` [EnumTextureDetectionModeGeneralWidthConcentration, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip, EnumTextureDetectionModeSkip]`

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See also**

[`EnumTextureDetectionMode`]({{ site.mobile_enum }}texture-detection-mode.html?lang=objc,swift)

### textFilterModes

Sets the mode and priority for text filter.

```objc
NSArray* textFilterModes[8]
```

**Value range**

Each array item can be any one of the [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift) Enumeration items.  

**Default value**

` [EnumTextFilterModeGeneralContour, EnumTextFilterModeSkip, EnumTextFilterModeSkip, EnumTextFilterModeSkip, EnumTextFilterModeSkip, EnumTextFilterModeSkip, EnumTextFilterModeSkip, EnumTextFilterModeSkip]`  

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is. If the image contains a lot of text, you can enable text filter to speed up the localization process.

**See also**

[`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=objc,swift)

### textAssistedCorrectionMode

Sets the mode of text assisted correction for barcode decoding. ***Not supported yet***.

```objc
EnumTextAssistedCorrectionMode textAssistedCorrectionMode
```

**Value range**

Any one of the `EnumTextAssistedCorrectionMode` Enumeration items.  

**Default value**

`EnumTextAssistedCorrectionModeVerifying`  

### dpmCodeReadingModes

Sets the mode and priority for DPM code reading.

```objc
NSArray* dpmCodeReadingModes[8]
```

**Value range**

Each array item can be any one of the [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift) Enumeration items.  

**Default value**

` [EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip, EnumDPMCodeReadingModeSkip]`  

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**

[`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=objc,swift)

### deformationResistingModes

Sets the mode and priority for deformation resisting.

```objc
NSArray* deformationResistingModes[8]
```

**Value range**

Each array item can be any one of the [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift) Enumeration items.

**Default value**

`[EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip, EnumDeformationResistingModeSkip]`  

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**

[`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=objc,swift)

### barcodeComplementModes

Sets the mode and priority to complement the missing parts in the barcode.

```objc
NSArray* barcodeComplementModes[8]
```

**Value range**

Each array item can be any one of the [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift) Enumeration items.  

**Default value**

`[EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip, EnumBarcodeComplementModeSkip]`  

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**
   [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=objc,swift)

### barcodeColourModes

Sets the mode and priority for the barcode colour mode used to process the barcode zone.

```objc
NSArray* barcodeColourModes[8]
```

**Value range**

Each array item can be any one of the [`EnumBarcodeColourMode`]({{ site.mobile_enum }}barcode-colour-mode.html?lang=objc,swift) Enumeration items.  

**Default value**

`[EnumBarcodeColourModeDarkOnLight, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip, EnumBarcodeColourModeSkip]`
**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**
   [`EnumBarcodeColourMode`]({{ site.mobile_enum }}barcode-colour-mode.html?lang=objc,swift)

### accompanyingTextRecognitionModes

Sets the mode and priority to recognize accompanying text.

```objc
NSArray* accompanyingTextRecognitionModes[8]
```

**Value range**

Each array item can be any one of the `EnumAccompanyingTextRecognitionMode` Enumeration items.  

**Default value**

` [EnumAccompanyingTextRecognitionModeSkip, EnumAccompanyingTextRecognitionModeSkip, EnumAccompanyingTextRecognitionModeSkip, EnumAccompanyingTextRecognitionModeSkip, EnumAccompanyingTextRecognitionModeSkip,  EnumAccompanyingTextRecognitionModeSkip, EnumAccompanyingTextRecognitionModeSkip, EnumAccompanyingTextRecognitionModeSkip]`  

**Remark**

The array index represents the priority of the item. The smaller index is, the higher priority is.  
