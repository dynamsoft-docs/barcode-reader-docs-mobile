---
layout: default-layout
title: TextResult index - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the TextResult index of Dynamsoft Barcode Reader for iOS SDK.
keywords: TextResult index, api reference, iOS
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-textresult-index-v9.6.20.html
---

# Barcode Result Classes

## [iTextResult](auxiliary-iTextResult.md)

`iTextResult` is the class that stores the text result data.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iTextResult : NSObject
```
2. 
```swift
class iTextResult : NSObject
```

| Attribute | Descriptions |
|-----------| ----------- |
| [`barcodeFormat`](auxiliary-iTextResult.md#barcodeformat) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](auxiliary-iTextResult.md#barcodeformat_2) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](auxiliary-iTextResult.md#barcodeformatstring) | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeText`](auxiliary-iTextResult.md#barcodetext) | The barcode text, ends by '\0'. |
| [`barcodeBytes`](auxiliary-iTextResult.md#barcodebytes) | The barcode content in a byte array. |
| [`localizationResult`](auxiliary-iTextResult.md#localizationresult) | The corresponding localization result. |
| [`detailedResult`](auxiliary-iTextResult.md#detailedresult) | One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.md), [`iPDF417Details`](auxiliary-iPDF417Details.md), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.md), [`iAztecDetails`](auxiliary-iAztecDetails.md), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.md). |
| [`extendedResults`](auxiliary-iTextResult.md#extendedresults) | The extended result array. |
| [`exception`](auxiliary-iTextResult.md#exception) | The exception message. |
| [`isDPM`](auxiliary-iTextResult.md#isdpm) | This attribute stands for whether the result is a DPM result. |
| [`isMirrored`](auxiliary-iTextResult.md#ismirrored) | This attribute stands for whether the barcode is mirrored. |

## [iLocalizationResult](auxiliary-iLocalizationResult.md)

`iLocalizationResult` is the extension of the class [`iTextResult`](auxiliary-iTextResult.md). It stores the localization result information.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iLocalizationResult : NSObject
```
2. 
```swift
class iLocalizationResult : NSObject
```

| Attribute | Descriptions |
|---------- | ----------- |
| [`terminatePhase`](auxiliary-iLocalizationResult.md#terminatephase) | The terminate phase of localization result. |
| [`barcodeFormat`](auxiliary-iLocalizationResult.md#barcodeformat) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](auxiliary-iLocalizationResult.md#barcodeformat_2 ) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](auxiliary-iLocalizationResult.md#barcodeformatstring) | Barcode type in BarcodeFormat group 1 as string. |
| [`resultPoints`](auxiliary-iLocalizationResult.md#resultpoints) | The vertices coordinates information of the barcode region. |
| [`angle`](auxiliary-iLocalizationResult.md#angle) | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](auxiliary-iLocalizationResult.md#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](auxiliary-iLocalizationResult.md#pagenumber) | The page number the barcode located in. The index is 0-based. |
| [`regionName`](auxiliary-iLocalizationResult.md#regionname) | The region name the barcode located in. |
| [`documentName`](auxiliary-iLocalizationResult.md#documentname)| The document name. |
| [`resultCoordinateType`](auxiliary-iLocalizationResult.md#resultcoordinatetype) | The coordinate type. |
| [`accompanyingTextBytes`](auxiliary-iLocalizationResult.md#accompanyingtextbytes) | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](auxiliary-iLocalizationResult.md#accompanyingtextbyteslength) | The length of the accompanying text byte array. |
| [`confidence`](auxiliary-iLocalizationResult.md#confidence) | The confidence of the localization result. |

## [iExtendedResult](auxiliary-iExtendedResult.md)

`iExtendedResult` is the extension of the class [`iTextResult`](auxiliary-iTextResult.md). It stores the extended result information.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iExtendedResult : NSObject
```
2. 
```swift
class iExtendedResult : NSObject
```  

| Attribute | Descriptions |
|---------- | ------------ |
| [`resultType`](auxiliary-iExtendedResult.md#resulttype) | The extended result type. |
| [`barcodeFormat`](auxiliary-iExtendedResult.md#barcodeformat) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](auxiliary-iExtendedResult.md#barcodeformat_2) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](auxiliary-iExtendedResult.md#barcodeformatstring) | Barcode type in BarcodeFormat group 1 as string. |
| [`confidence`](auxiliary-iExtendedResult.md#confidence) | The confidence of the result. The higher confidence means the higher accuracy. |
| [`bytes`](auxiliary-iExtendedResult.md#bytes) | The content in a byte array. |
| [`bytesLength`](auxiliary-iExtendedResult.md#byteslength) | The length of the byte array. |
| [`accompanyingTextBytes`](auxiliary-iExtendedResult.md#accompanyingtextbytes) | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](auxiliary-iExtendedResult.md#accompanyingtextbyteslength) | The length of the accompanying text byte array. |
| [`deformation`](auxiliary-iExtendedResult.md#deformation) | The deformation value. |
| [`detailedResult`](auxiliary-iExtendedResult.md#detailedresult) | One of the following: [`iQRCodeDetails`](auxiliary-iQuadrilateral.md), [`iPDF417Details`](auxiliary-iPDF417Details.md), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.md), [`iAztecDetails`](auxiliary-iAztecDetails.md), [`OneDCodeDetails`](auxiliary-iOneDCodeDetails.md). |
| [`samplingImage`](auxiliary-iExtendedResult.md#samplingimage) | The sampling image info. |
| [`clarity`](auxiliary-iExtendedResult.md#clarity) | The clarity of the barcode zone in percentage. |

## [iAztecDetails](auxiliary-iAztecDetails.md)

`iAztecDetails` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the Aztec code details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iAztecDetails : NSObject
```
2. 
```swift
class iAztecDetails : NSObject
```

| Attribute | Descriptions |
|---------- | ------------ |
| [`moduleSize`](auxiliary-iAztecDetails.md#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-iAztecDetails.md#rows) | The row count of the barcode. |
| [`columns`](auxiliary-iAztecDetails.md#columns) | The column count of the barcode. |
| [`layerNumber`](auxiliary-iAztecDetails.md#layernumber) | A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code. |

## [iDataMatrixDetails](auxiliary-iDataMatrixDetails.md)

`iDataMatrixDetails` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the DataMatrix code details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iDataMatrixDetails : NSObject
```
2. 
```swift
class iDataMatrixDetails : NSObject
```

| Attribute | Descriptions |
|---------- | ------------ |
| [`moduleSize`](auxiliary-iDataMatrixDetails.md#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-iDataMatrixDetails.md#rows) | The row count of the barcode. |
| [`columns`](auxiliary-iDataMatrixDetails.md#columns) | The column count of the barcode. |
| [`dataRegionRows`](auxiliary-iDataMatrixDetails.md#dataregionrows) | The data region row count of the barcode. |
| [`dataRegionColumns`](auxiliary-iDataMatrixDetails.md#dataregioncolumns) | The data region column count of the barcode. |
| [`dataRegionNumber`](auxiliary-iDataMatrixDetails.md#dataregionnumber) | The data region count. |

## [iOneDCodeDetails](auxiliary-iOneDCodeDetails.md)

`iOneDCodeDetails` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the OneD code details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iOneDCodeDetails : NSObject
```
2. 
```swift
class iOneDCodeDetails : NSObject
```  

| Attribute | Descriptions |
|---------- | ------------ |
| [`moduleSize`](auxiliary-iOneDCodeDetails.md#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`startCharsBytes`](auxiliary-iOneDCodeDetails.md#startcharsbytes) | The start chars in a byte array. |
| [`startCharsBytesLength`](auxiliary-iOneDCodeDetails.md#startcharsbyteslength) | The length of the start chars byte array. |
| [`stopCharsBytes`](auxiliary-iOneDCodeDetails.md#stopcharsbytes) | The stop chars in a byte array. |
| [`stopCharsBytesLength`](auxiliary-iOneDCodeDetails.md#stopcharsbyteslength) | The length of the stop chars byte array. |
| [`checkDigitBytes`](auxiliary-iOneDCodeDetails.md#checkdigitbytes) | The check digit chars in a byte array. |
| [`checkDigitBytesLength`](auxiliary-iOneDCodeDetails.md#checkdigitbyteslength) | The length of the check digit chars byte array. |

## [iPDF417Details](auxiliary-iPDF417Details.md)

`iPDF417Details` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the PDF417 code details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iPDF417Details : NSObject
```
2. 
```swift
class iPDF417Details : NSObject
```

| Attribute | Descriptions |
|---------- | ------------ |
| [`moduleSize`](auxiliary-iPDF417Details.md#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-iPDF417Details.md#rows) | The row count of the barcode. |
| [`columns`](auxiliary-iPDF417Details.md#columns) | The column count of the barcode. |
| [`errorCorrectionLevel`](auxiliary-iPDF417Details.md#errorcorrectionlevel) | The error correction level of the barcode. |

## [iQRCodeDetails](auxiliary-iQRCodeDetails.md)

`iQRCodeDetails` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the QRCode details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iQRCodeDetails : NSObject
```
2. 
```swift
class iQRCodeDetails : NSObject
```

| Attribute | Descriptions |
|---------- | ------------ |
| [`moduleSize`](auxiliary-iQRCodeDetails.md#modulesize) | The barcode module size (the minimum bar width in pixels). |
| [`rows`](auxiliary-iQRCodeDetails.md#rows) | The row count of the barcode.   |
| [`columns`](auxiliary-iQRCodeDetails.md#columns) | The column count of the barcode. |
| [`errorCorrectionLevel`](auxiliary-iQRCodeDetails.md#errorcorrectionlevel) | The error correction level of the barcode.   |
| [`version`](auxiliary-iQRCodeDetails.md#version) | The version of the QR Code. |
| [`model`](auxiliary-iQRCodeDetails.md#model) | Number of the models. |
| [`mode`](auxiliary-iQRCodeDetails.md#mode) | Identify the first data encoding mode. |
| [`page`](auxiliary-iQRCodeDetails.md#page) | Identify the position of the particular symbol. |
| [`totalPage`](auxiliary-iQRCodeDetails.md#totalpage) | Identify the total number of symbols to be concatenated in the Structured Append format. |
| [`parityData`](auxiliary-iQRCodeDetails.md#paritydata) | The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks. |

## [iSamplingImageData](auxiliary-iSamplingImageData.md)

`iSamplingImageData` stores the detailed image data in `iExtendedResult`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iSamplingImageData : NSObject
```
2. 
```swift
class iSamplingImageData : NSObject
```

| Attribute | Descriptions |
|---------- | ----------- |
| [`bytes`](auxiliary-iSamplingImageData.md#bytes) | The sampling image data in a byte array. |
| [`width`](auxiliary-iSamplingImageData.md#width) | The width of the sampling image. |
| [`height`](auxiliary-iSamplingImageData.md#height) | The height of the sampling image. |
