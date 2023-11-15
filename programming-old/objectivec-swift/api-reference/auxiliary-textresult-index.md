---
layout: default-layout
title: TextResult index - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the TextResult index of Dynamsoft Barcode Reader for iOS SDK.
keywords: TextResult index, api reference, iOS
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-textresult-index.html
---

# Barcode Result Classes

## [iTextResult](auxiliary-iTextResult.html)

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
| [`barcodeFormat`](auxiliary-iTextResult.html#barcodeformat) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](auxiliary-iTextResult.html#barcodeformat_2) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](auxiliary-iTextResult.html#barcodeformatstring) | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeText`](auxiliary-iTextResult.html#barcodetext) | The barcode text, ends by '\0'. |
| [`barcodeBytes`](auxiliary-iTextResult.html#barcodebytes) | The barcode content in a byte array. |
| [`localizationResult`](auxiliary-iTextResult.html#localizationresult) | The corresponding localization result. |
| [`detailedResult`](auxiliary-iTextResult.html#detailedresult) | One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.html), [`iPDF417Details`](auxiliary-iPDF417Details.html), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.html), [`iAztecDetails`](auxiliary-iAztecDetails.html), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.html). |
| [`extendedResults`](auxiliary-iTextResult.html#extendedresults) | The extended result array. |
| [`exception`](auxiliary-iTextResult.html#exception) | The exception message. |
| [`isDPM`](auxiliary-iTextResult.html#isdpm) | This attribute stands for whether the result is a DPM result. |
| [`isMirrored`](auxiliary-iTextResult.html#ismirrored) | This attribute stands for whether the barcode is mirrored. |

## [iLocalizationResult](auxiliary-iLocalizationResult.html)

`iLocalizationResult` is the extension of the class [`iTextResult`](auxiliary-iTextResult.html). It stores the localization result information.

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
| [`terminatePhase`](auxiliary-iLocalizationResult.html#terminatephase) | The terminate phase of localization result. |
| [`barcodeFormat`](auxiliary-iLocalizationResult.html#barcodeformat) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](auxiliary-iLocalizationResult.html#barcodeformat_2 ) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](auxiliary-iLocalizationResult.html#barcodeformatstring) | Barcode type in BarcodeFormat group 1 as string. |
| [`resultPoints`](auxiliary-iLocalizationResult.html#resultpoints) | The vertices coordinates information of the barcode region. |
| [`angle`](auxiliary-iLocalizationResult.html#angle) | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](auxiliary-iLocalizationResult.html#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](auxiliary-iLocalizationResult.html#pagenumber) | The page number the barcode located in. The index is 0-based. |
| [`regionName`](auxiliary-iLocalizationResult.html#regionname) | The region name the barcode located in. |
| [`documentName`](auxiliary-iLocalizationResult.html#documentname)| The document name. |
| [`resultCoordinateType`](auxiliary-iLocalizationResult.html#resultcoordinatetype) | The coordinate type. |
| [`accompanyingTextBytes`](auxiliary-iLocalizationResult.html#accompanyingtextbytes) | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](auxiliary-iLocalizationResult.html#accompanyingtextbyteslength) | The length of the accompanying text byte array. |
| [`confidence`](auxiliary-iLocalizationResult.html#confidence) | The confidence of the localization result. |

## [iExtendedResult](auxiliary-iExtendedResult.html)

`iExtendedResult` is the extension of the class [`iTextResult`](auxiliary-iTextResult.html). It stores the extended result information.

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
| [`resultType`](auxiliary-iExtendedResult.html#resulttype) | The extended result type. |
| [`barcodeFormat`](auxiliary-iExtendedResult.html#barcodeformat) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](auxiliary-iExtendedResult.html#barcodeformat_2) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](auxiliary-iExtendedResult.html#barcodeformatstring) | Barcode type in BarcodeFormat group 1 as string. |
| [`confidence`](auxiliary-iExtendedResult.html#confidence) | The confidence of the result. The higher confidence means the higher accuracy. |
| [`bytes`](auxiliary-iExtendedResult.html#bytes) | The content in a byte array. |
| [`bytesLength`](auxiliary-iExtendedResult.html#byteslength) | The length of the byte array. |
| [`accompanyingTextBytes`](auxiliary-iExtendedResult.html#accompanyingtextbytes) | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](auxiliary-iExtendedResult.html#accompanyingtextbyteslength) | The length of the accompanying text byte array. |
| [`deformation`](auxiliary-iExtendedResult.html#deformation) | The deformation value. |
| [`detailedResult`](auxiliary-iExtendedResult.html#detailedresult) | One of the following: [`iQRCodeDetails`](auxiliary-iQuadrilateral.html), [`iPDF417Details`](auxiliary-iPDF417Details.html), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.html), [`iAztecDetails`](auxiliary-iAztecDetails.html), [`OneDCodeDetails`](auxiliary-iOneDCodeDetails.html). |
| [`samplingImage`](auxiliary-iExtendedResult.html#samplingimage) | The sampling image info. |
| [`clarity`](auxiliary-iExtendedResult.html#clarity) | The clarity of the barcode zone in percentage. |

## [iAztecDetails](auxiliary-iAztecDetails.html)

`iAztecDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the Aztec code details.

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
| [`moduleSize`](auxiliary-iAztecDetails.html#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-iAztecDetails.html#rows) | The row count of the barcode. |
| [`columns`](auxiliary-iAztecDetails.html#columns) | The column count of the barcode. |
| [`layerNumber`](auxiliary-iAztecDetails.html#layernumber) | A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code. |

## [iDataMatrixDetails](auxiliary-iDataMatrixDetails.html)

`iDataMatrixDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the DataMatrix code details.

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
| [`moduleSize`](auxiliary-iDataMatrixDetails.html#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-iDataMatrixDetails.html#rows) | The row count of the barcode. |
| [`columns`](auxiliary-iDataMatrixDetails.html#columns) | The column count of the barcode. |
| [`dataRegionRows`](auxiliary-iDataMatrixDetails.html#dataregionrows) | The data region row count of the barcode. |
| [`dataRegionColumns`](auxiliary-iDataMatrixDetails.html#dataregioncolumns) | The data region column count of the barcode. |
| [`dataRegionNumber`](auxiliary-iDataMatrixDetails.html#dataregionnumber) | The data region count. |

## [iOneDCodeDetails](auxiliary-iOneDCodeDetails.html)

`iOneDCodeDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the OneD code details.

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
| [`moduleSize`](auxiliary-iOneDCodeDetails.html#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`startCharsBytes`](auxiliary-iOneDCodeDetails.html#startcharsbytes) | The start chars in a byte array. |
| [`startCharsBytesLength`](auxiliary-iOneDCodeDetails.html#startcharsbyteslength) | The length of the start chars byte array. |
| [`stopCharsBytes`](auxiliary-iOneDCodeDetails.html#stopcharsbytes) | The stop chars in a byte array. |
| [`stopCharsBytesLength`](auxiliary-iOneDCodeDetails.html#stopcharsbyteslength) | The length of the stop chars byte array. |
| [`checkDigitBytes`](auxiliary-iOneDCodeDetails.html#checkdigitbytes) | The check digit chars in a byte array. |
| [`checkDigitBytesLength`](auxiliary-iOneDCodeDetails.html#checkdigitbyteslength) | The length of the check digit chars byte array. |

## [iPDF417Details](auxiliary-iPDF417Details.html)

`iPDF417Details` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the PDF417 code details.

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
| [`moduleSize`](auxiliary-iPDF417Details.html#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-iPDF417Details.html#rows) | The row count of the barcode. |
| [`columns`](auxiliary-iPDF417Details.html#columns) | The column count of the barcode. |
| [`errorCorrectionLevel`](auxiliary-iPDF417Details.html#errorcorrectionlevel) | The error correction level of the barcode. |

## [iQRCodeDetails](auxiliary-iQRCodeDetails.html)

`iQRCodeDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the QRCode details.

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
| [`moduleSize`](auxiliary-iQRCodeDetails.html#modulesize) | The barcode module size (the minimum bar width in pixels). |
| [`rows`](auxiliary-iQRCodeDetails.html#rows) | The row count of the barcode.   |
| [`columns`](auxiliary-iQRCodeDetails.html#columns) | The column count of the barcode. |
| [`errorCorrectionLevel`](auxiliary-iQRCodeDetails.html#errorcorrectionlevel) | The error correction level of the barcode.   |
| [`version`](auxiliary-iQRCodeDetails.html#version) | The version of the QR Code. |
| [`model`](auxiliary-iQRCodeDetails.html#model) | Number of the models. |
| [`mode`](auxiliary-iQRCodeDetails.html#mode) | Identify the first data encoding mode. |
| [`page`](auxiliary-iQRCodeDetails.html#page) | Identify the position of the particular symbol. |
| [`totalPage`](auxiliary-iQRCodeDetails.html#totalpage) | Identify the total number of symbols to be concatenated in the Structured Append format. |
| [`parityData`](auxiliary-iQRCodeDetails.html#paritydata) | The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks. |

## [iSamplingImageData](auxiliary-iSamplingImageData.html)

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
| [`bytes`](auxiliary-iSamplingImageData.html#bytes) | The sampling image data in a byte array. |
| [`width`](auxiliary-iSamplingImageData.html#width) | The width of the sampling image. |
| [`height`](auxiliary-iSamplingImageData.html#height) | The height of the sampling image. |
