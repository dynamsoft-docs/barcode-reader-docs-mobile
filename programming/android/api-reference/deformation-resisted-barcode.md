---
layout: default-layout
title: DeformationResistedBarcode Class - Dynamsoft Barcode Reader Android Edition
description: The DeformationResistedBarcode class of Dynamsoft Barcode Reader Android represents the information of a deformation resisted barcode with the image data, location and format.
keywords: GetImageData, DeformationResistedBarcode, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DeformationResistedBarcode
permalink: /programming/android/api-reference/deformation-resisted-barcode.html
---

# DeformationResistedBarcode Class

`DeformationResistedBarcode` is a class that represents a deformation-resisted barcode.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class DeformationResistedBarcode
```

## Attributes & Methods

| Attribute | Description |
| ------ | ----------- |
| [`imageData`](#imagedata) | The deformation-resisted barcode image data. |
| [`location`](#location) | The location of the deformation-resisted barcode. |
| [`format`](#format) | The format of the deformation-resisted barcode. |

| Method | Description |
| ------ | ----------- |
| [`DeformationResistedBarcode`](#deformationresistedbarcode) | The constructor. |

### imageData

An [`ImageData`]({{ site.dcvb_android_api }}core/basic-structures/image-data.html) object representing the deformation-resisted barcode image.

```java
ImageData imageData;
```

### location

The location of the deformation-resisted barcode within the image represented as a [`Quadrilateral`]({{ site.dcvb_android_api }}core/basic-structures/quadrilateral.html).

```java
Quadrilateral location;
```

### format

A [`EnumBarcodeFormat`]({{site.dbr_android_api }}enum/barcode-format.html?lang=android) enum that represents the format of the deformation-resisted barcode.

```java
long format;
```

### DeformationResistedBarcode

The constructor.

```java
DeformationResistedBarcode(ImageData imageData, @NonNull Quadrilateral location, @EnumBarcodeFormat long format);
```
