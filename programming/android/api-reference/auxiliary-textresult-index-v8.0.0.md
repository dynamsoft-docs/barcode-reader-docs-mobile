---
layout: default-layout
title: TextResult index - Dynamsoft Barcode Reader Android API Reference
description: This page shows the TextResult index of Dynamsoft Barcode Reader for Android SDK.
keywords: TextResult index, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/android/api-reference/auxiliary-textresult-index-v8.0.0.html
---

# Barcode Result Classes

## [TextResult](auxiliary-TextResult.html)

`TextResult` is the class that stores the text result data.

```java
class com.dynamsoft.dbr.TextResult;
```

| Attribute | Type | Descriptions |
| --------- | ---- | ------------ |
| [`barcodeFormat`](auxiliary-TextResult.html#barcodeformat) | *int* | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](auxiliary-TextResult.html#barcodeformatstring) | *String* | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](auxiliary-TextResult.html#barcodeformat_2) | *int* | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](auxiliary-TextResult.html#barcodeformatstring_2) | *String* | Barcode type in BarcodeFormat group 2 as string. |
| [`barcodeText`](auxiliary-TextResult.html#barcodetext) | *String* | The barcode text, ends by '\0'. |
| [`barcodeBytes`](auxiliary-TextResult.html#barcodebytes) | *byte\[\]* | The barcode content in a byte array. |
| [`localizationResult`](auxiliary-TextResult.html#localizationresult) | [`LocalizationResult`](auxiliary-LocalizationResult.html)\* | The corresponding localization result. |
| [`detailedResult`](auxiliary-TextResult.html#detailedresult) | *Object* | One of the following: [`QRCodeDetails`](auxiliary-QRCodeDetails.html), [`PDF417Details`](auxiliary-PDF417Details.html), [`DataMatrixDetails`](auxiliary-DataMatrixDetails.html), [`AztecDetails`](auxiliary-AztecDetails.html), [`OneDCodeDetails`](auxiliary-OneDCodeDetails.html). |
| [`results`](auxiliary-TextResult.html#results) | [`ExtendedResult`](auxiliary-ExtendedResult.html)\[\] | The extended result array. |

**Code Snippet**

```java
// Get the text result by decode methodes
TextResult[] textresult = barcodeReader.decodeBuffer(frame.getData(),frame.getWidth(),frame.getHeight(),frame.getStrides()[0],frame.getFormat(),"");
```

## [LocalizationResult](auxiliary-LocalizationResult.html)

`LocalizationResult` is the extension of the class [`TextResult`](auxiliary-TextResult.html). It stores the localization result information.

```java
class com.dynamsoft.dbr.LocalizationResult;
```

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
| [`pageNumber`](auxiliary-LocalizationResult.html#oagenumber) | *int* | The page number the barcode located in. The index is 0-based. |
| [`regionName`](auxiliary-LocalizationResult.html#regionname) | *String* | The region name the barcode located in. |
| [`documentName`](auxiliary-LocalizationResult.html#documentname) | *String* | The document name. |
| [`resultCoordinateType`](auxiliary-LocalizationResult.html#resultcoordinatetype) | *int* | The coordinate type. |
| [`accompanyingTextBytes`](auxiliary-LocalizationResult.html#accompanyingtextbytes) | *byte\[\]* | The accompanying text content in a byte array. |
| [`confidence`](auxiliary-LocalizationResult.html#confidence) | *int* | The confidence of the localization result. |

**Code Snippet**

```java
if ( textresult != null && textresult.length != 0){
    for ( int i = 0; i< textresult.length; i++ ) {
        LocalizationResult localizationResult = textresult[i].localizationResult;
        // DO something on localization results.
    }
}
```

## [ExtendedResult](auxiliary-ExtendedResult.html)

`ExtendedResult` is the extension of the class [`TextResult`](auxiliary-TextResult.html). It stores the extended result information.

```java
class com.dynamsoft.dbr.ExtendedResult;
```

| Attribute | Type | Description |
|---------- |------|-------------|
| [`resultType`](auxiliary-ExtendedResult.html#resulttype) | *int* | The extended result type. |
| [`barcodeFormat`](auxiliary-ExtendedResult.html#barcodeformat) | *int* | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](auxiliary-ExtendedResult.html#barcodeformatstring) | *String* | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](auxiliary-ExtendedResult.html#barcodeformat_2) | *int* | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](auxiliary-ExtendedResult.html#barcodeformatstring_2) | *String* | Barcode type in BarcodeFormat group 2 as string. |
| [`confidence`](auxiliary-ExtendedResult.html#confidence) | *int* | The confidence of the result. The higher confidence means the higher accuracy. |
| [`bytes`](auxiliary-ExtendedResult.html#bytes) | *byte\[\]* | The content in a byte array. |
| [`accompanyingTextBytes`](auxiliary-ExtendedResult.html#accompanyingtextbytes) | *byte\[\]* | The accompanying text content in a byte array. |
| [`deformation`](auxiliary-ExtendedResult.html#deformation) | *int* | The deformation value. |
| [`detailedResult`](auxiliary-ExtendedResult.html#detailedresult) | *Object* | One of the following: [`QRCodeDetails`](auxiliary-QRCodeDetails.html), [`PDF417Details`](auxiliary-PDF417Details.html), [`DataMatrixDetails`](auxiliary-DataMatrixDetails.html), [`AztecDetails`](auxiliary-AztecDetails.html), [`OneDCodeDetails`](auxiliary-OneDCodeDetails.html). |
| [`samplingImage`](auxiliary-ExtendedResult.html#samplingimage) | [`SamplingImageData`](auxiliary-SamplingImageData.html) | The sampling image info. |
| [`clarity`](auxiliary-ExtendedResult.html#clarity) | *int* | The clarity of the barcode zone in percentage. |

**Code Snippet**

```java
if ( textresult != null && textresult.length != 0){
    for ( int i = 0; i < textresult.length; i++ ) {
        ExtendedResult[] extendedResult = textresult[i].results;
        // Do something on extended results.
    }
}
```

## [AztecDetails](auxiliary-AztecDetails.html)

`AztecDetails` is one of the [`detailedResult`](auxiliary-TextResult.html#detailedresult) in class `TextResult`. It stores the Aztec code details.

```java
class com.dynamsoft.dbr.AztecDetails;
```

| Attribute | Type | Description |
|---------- | -----|------ |
| [`moduleSize`](auxiliary-AztecDetails.html#modulesize) | *int* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-AztecDetails.html#rows) | *int* | The row count of the barcode. |
| [`columns`](auxiliary-AztecDetails.html#columns) | *int* | The column count of the barcode. |
| [`layerNumber`](auxiliary-AztecDetails.html#layernumber) | *int* | A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code. |

**Code Snippet**

```java
//The textresult[i] is one of the text result you got  
AztecDetails aztecDetails = (AztecDetails) textresult[i].detailedResult;
```

## [DataMatrixDetails](auxiliary-DataMatrixDetails.html)

`DataMatrixDetails` is one of the [`detailedResult`](auxiliary-TextResult.html#detailedresult) in class `TextResult`. It stores the DataMatrix code details.

```java
class com.dynamsoft.dbr.DataMatrixDetails;
```

| Attribute | Type | Description |
|---------- |-----|------|
| [`moduleSize`](auxiliary-DataMatrixDetails.html#modulesize) | *int* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-DataMatrixDetails.html#rows) | *int* | The row count of the barcode. |
| [`columns`](auxiliary-DataMatrixDetails.html#columns) | *int* | The column count of the barcode. |
| [`dataRegionRows`](auxiliary-DataMatrixDetails.html#dataregionrows) | *int* | The data region row count of the barcode. |
| [`dataRegionColumns`](auxiliary-DataMatrixDetails.html#dataregioncolumns) | *int* | The data region column count of the barcode. |
| [`dataRegionNumber`](auxiliary-DataMatrixDetails.html#dataregionnumber) | *int* | The data region count. |

**Code Snippet**

```java
//The textresult[i] is one of the text result you got  
DataMatrixDetails dataMatrixDetails = (DataMatrixDetails) textresult[i].detailedResult;
```

## [OneDCodeDetails](auxiliary-OneDCodeDetails.html)

`OneDCodeDetails` is one of the [`detailedResult`](auxiliary-TextResult.html#detailedresult) in class `TextResult`. It stores the OneD code details.

```java
class com.dynamsoft.dbr.OneDCodeDetails;
```

| Attribute | Type | Description |
|---------- |-----| ---- |
| [`moduleSize`](auxiliary-OneDCodeDetails.html#modulesize) | *int* | The barcode module size (the minimum bar width in pixel). |
| [`startCharsBytes`](auxiliary-OneDCodeDetails.html#startcharsbytes) | *int* | The start chars in a byte array. |
| [`stopCharsBytes`](auxiliary-OneDCodeDetails.html#stopcharsbytes) | *int* | The stop chars in a byte array. |
| [`checkDigitBytes`](auxiliary-OneDCodeDetails.html#checkdigitbytes) | *int* | The check digit chars in a byte array. |
| [`startPatternRange`](auxiliary-OneDCodeDetails.html#startpatternrange) | *int* | The start pattern range of the OneDcode. |
| [`middlePatternRange`](auxiliary-OneDCodeDetails.html#middlepatternrange) | *int* | The middle pattern range of the OneDcode. |
| [`endPatternRange`](auxiliary-OneDCodeDetails.html#endpatternrange) | *int* | The end pattern range of the OneDcode. |

**Code Snippet**

```java
//The textresult[i] is one of the text result you got  
OneDCodeDetails oneDDetails = (OneDCodeDetails) textresult[i].detailedResult;
```

## [PDF417Details](auxiliary-PDF417Details.html)

`PDF417Details` is one of the [`detailedResult`](auxiliary-TextResult.html#detailedresult) in class `TextResult`. It stores the PDF417 code details.

```java
class com.dynamsoft.dbr.PDF417Details;
```

| Attribute | Type | Description |
|---------- |------|------------ |
| [`moduleSize`](auxiliary-PDF417Details.html#modulesize) | *int* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-PDF417Details.html#rows) | *int* | The row count of the barcode. |
| [`columns`](auxiliary-PDF417Details.html#columns) | *int* | The column count of the barcode. |
| [`errorCorrectionLevel`](auxiliary-PDF417Details.html#errorcorrectionlevel) | *int* | The error correction level of the barcode. |

**Code Snippet**

```java
//The textresult[i] is one of the text results you got  
PDF417Details pdf417Details = (PDF417Details) textresult[i].detailedResult;
```

## [QRCodeDetails](auxiliary-QRCodeDetails.html)

`QRCodeDetails` is one of the [`detailedResult`](auxiliary-TextResult.html#detailedresult) in class `TextResult`. It stores the QRCode details.

```java
class com.dynamsoft.dbr.QRCodeDetails;
```

| Attribute | Type | Description |
|---------- | ---- |-----|
| [`moduleSize`](auxiliary-QRCodeDetails.html#modulesize) | *int* | The barcode module size (the minimum bar width in pixels). |
| [`rows`](auxiliary-QRCodeDetails.html#rows) | *int* | The row count of the barcode.   |
| [`columns`](auxiliary-QRCodeDetails.html#columns) | *int* | The column count of the barcode. |
| [`errorCorrectionLevel`](auxiliary-QRCodeDetails.html#errorcorrectionlevel) | *int* | The error correction level of the barcode.   |
| [`version`](auxiliary-QRCodeDetails.html#version) | *int* | The version of the QR Code. |
| [`model`](auxiliary-QRCodeDetails.html#model) | *int* | Number of the models. |

**Code Snippet**

```java
//The textresult[i] is one of the text results you got  
QRCodeDetails qrDetails = (QRCodeDetails) textresult[i].detailedResult;
```

## [SamplingImageData](auxiliary-SamplingImageData.html)

`SamplingImageData` stores the detailed image data in `ExtendedResult`.

```java
class com.dynamsoft.dbr.SamplingImageData;
```

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`bytes`](auxiliary-SamplingImageData.html#bytes) | *byte\[\]* | The sampling image data in a byte array. |
| [`width`](auxiliary-SamplingImageData.html#width) | *int* | The width of the sampling image. |
| [`height`](auxiliary-SamplingImageData.html#height) | *int* | The height of the sampling image. |

**Code Snippet**

```java
SamplingImageData samplingImageData = extendedResult[j].samplingImage;
```
