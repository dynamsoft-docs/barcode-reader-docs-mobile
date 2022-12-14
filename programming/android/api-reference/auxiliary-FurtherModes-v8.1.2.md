---
layout: default-layout
title: FurtherModes Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the FurtherModes Class of Dynamsoft Barcode Reader for Android SDK.
keywords: FurtherModes, class, api reference, android
needAutoGenerateSidebar: true
permalink: /programming/android/api-reference/auxiliary-FurtherModes-v8.1.2.html
---


# FurtherModes

Stores the FurtherModes.

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`colourClusteringModes`](#colourclusteringmodes) | *int\[\]* |
| [`colourConversionModes`](#colourconversionmodes) | *int\[\]* |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *int\[\]* |
| [`regionPredetectionModes`](#regionpredetectionmodes) | *int\[\]* |
| [`imagePreprocessingModes`](#imagepreprocessingmodes) | *int\[\]* |
| [`textureDetectionModes`](#texturedetectionmodes) | *int\[\]* |
| [`textFilterModes`](#textfiltermodes) | *int\[\]* |
| [`dpmCodeReadingModes`](#dpmcodereadingmodes) | *int\[\]* |
| [`deformationResistingModes`](#deformationresistingmodes) | *int\[\]* |
| [`barcodeComplementModes`](#barcodecomplementmodes) | *int\[\]* |
| [`barcodeColourModes`](#barcodecolourmodes) | *int\[\]* |

### colourClusteringModes

Sets the mode and priority for colour categorization. Not supported yet.  

```java
int[] com.dynamsoft.dbr.FurtherModes.colourClusteringModes
```

**Value range**

Each array item can be any one of the [`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=android) Enumeration items.  

**Default value**

`[CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is. 

**See also**

[`EnumColourClusteringMode`]({{ site.mobile_enum }}colour-clustering-mode.html?lang=android)

### colourConversionModes

Sets the mode and priority for converting a colour image to a grayscale image.

```java
int[] com.dynamsoft.dbr.FurtherModes.colourConversionModes
```

**Value range**

Each array item can be any one of the [`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=android) Enumeration items.

**Default value**

`[CICM_GENERAL,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**

[`EnumColourConversionMode`]({{ site.mobile_enum }}colour-conversion-mode.html?lang=android)

### grayscaleTransformationModes

Sets the mode and priority for the grayscale image conversion.

```java
int[] com.dynamsoft.dbr.FurtherModes.grayscaleTransformationModes
```

**Value range**

Each array item can be any one of the [`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=android) Enumeration items.

**Default value**

`[GTM_ORIGINAL,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**

[`EnumGrayscaleTransformationMode`]({{ site.mobile_enum }}grayscale-transformation-mode.html?lang=android)

### regionPredetectionModes

Sets the region pre-detection mode for barcodes search.

```java
int[] com.dynamsoft.dbr.FurtherModes.regionPredetectionModes
```

**Value range**

Each array item can be any one of the [`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=android) Enumeration items.  

**Default value**

`[RPM_GENERAL,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is. If the image is large and the barcode on the image is very small, it is recommended to enable region predetection to speed up the localization process and recognition accuracy.

**See also**

[`EnumRegionPredetectionMode`]({{ site.mobile_enum }}region-predetection-mode.html?lang=android)

### imagePreprocessingModes

Sets the mode and priority for image preprocessing algorithms.

```java
int[] com.dynamsoft.dbr.FurtherModes.imagePreprocessingModes
```

**Value range**

Each array item can be any one of the [`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=android) Enumeration items.  

**Default value**

`[IPM_GENERAL,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See also**

[`EnumImagePreprocessingMode`]({{ site.mobile_enum }}image-preprocessing-mode.html?lang=android)

### textureDetectionModes

Sets the mode and priority for texture detection.

```java
int[] com.dynamsoft.dbr.FurtherModes.textureDetectionModes
```

**Value range**

Each array item can be any one of the [`EnumTextureDetectionMode`]({{ site.mobile_enum }}texture-detection-mode.html?lang=android) Enumeration items.  

**Default value**

`[TDM_GENERAL_WIDTH_CONCENTRATION,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See also**

[`EnumTextureDetectionMode`]({{ site.mobile_enum }}texture-detection-mode.html?lang=android)

### textFilterModes

Sets the mode and priority for text filter.

```java
int[] com.dynamsoft.dbr.FurtherModes.textFilterModes
```

**Value range**

Each array item can be any one of the [`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=android) Enumeration items.  

**Default value**

`[TFM_GENERAL_CONTOUR,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is. If the image contains a lot of text, you can enable text filter to speed up the localization process.

**See also**

[`EnumTextFilterMode`]({{ site.mobile_enum }}text-filter-mode.html?lang=android)

### dpmCodeReadingModes

Sets the mode and priority for DPM code reading.

```java
int[] com.dynamsoft.dbr.FurtherModes.dpmCodeReadingModes
```

**Value range**

Each array item can be any one of the [`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=android) Enumeration items.  

**Default value**

`[DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**

[`EnumDPMCodeReadingMode`]({{ site.mobile_enum }}dpm-code-reading-mode.html?lang=android)

### deformationResistingModes

Sets the mode and priority for deformation resisting.

```java
int[] com.dynamsoft.dbr.FurtherModes.deformationResistingModes
```

**Value range**

Each array item can be any one of the [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=android) Enumeration items.  

**Default value**

`[DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**

[`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=android) 

### barcodeComplementModes

Sets the mode and priority to complement the missing parts in the barcode.

```java
int[] com.dynamsoft.dbr.FurtherModes.barcodeComplementModes
```

**Value range**

Each array item can be any one of the [`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=android) Enumeration items.  

**Default value**

`[BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**

[`EnumBarcodeComplementMode`]({{ site.mobile_enum }}barcode-complement-mode.html?lang=android) 

### barcodeColourModes

Sets the mode and priority for the barcode colour mode used to process the barcode zone.

```java
int[] com.dynamsoft.dbr.FurtherModes.barcodeColourModes
```

**Value range**

Each array item can be any one of the [`EnumBarcodeColourMode`]({{ site.mobile_enum }}barcode-colour-mode.html?lang=android) Enumeration items.  

**Default value**

`[BICM_DARK_ON_LIGHT,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP]`  

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.  

**See also**
   [`EnumBarcodeColourMode`]({{ site.mobile_enum }}barcode-colour-mode.html?lang=android)
