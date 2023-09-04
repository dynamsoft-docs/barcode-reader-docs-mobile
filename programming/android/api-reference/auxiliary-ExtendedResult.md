---
layout: default-layout
title: ExtendedBarcodeResult Class - Dynamsoft Barcode Reader Android Edition
description: ExtendedBarcodeResult class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.
keywords: ExtendedBarcodeResult, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ExtendedBarcodeResult
permalink: /programming/android/api-reference/auxiliary-ExtendedResult.html
---


# ExtendedBarcodeResult

The `ExtendedBarcodeResult` class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class ExtendedBarcodeResult extends DecodedBarcodeElement
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getExtendedBarcodeResultType`](#getextendedbarcoderesulttype) | Get the type of the extended barcode result. |
| [`getDeformation`](#getdeformation) | Get the deformation level of the barcode zone. |
| [`getClarity`](#getclarity) | Get the clarity level of the barcode zone. |
| [`getSamplingImage`](#getsamplingimage) | Get the sampling image of the barcode zone. |

### getExtendedBarcodeResultType

Get the type of the extended barcode result.

```java
EnumExtendedBarcodeResultType getExtendedBarcodeResultType();
```

**Return Value**

The type of the extended barcode result.

### getDeformation

Get the deformation level of the barcode zone.

```java
int getDeformation();
```

**Return Value**

The deformation level of the barcode zone.

### getClarity

Get the clarity level of the barcode zone.

```java
int getClarity();
```

**Return Value**

The clarity level of the barcode zone.

### getSamplingImage

Get the sampling image of the barcode zone.

```java
ImageData getSamplingImage();
```

**Return Value**

An ImageData object as the sampling image of the barcode zone.
