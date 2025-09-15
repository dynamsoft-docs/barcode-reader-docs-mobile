---
layout: default-layout
title: TextResult index - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the TextResult index of Dynamsoft Barcode Reader for iOS SDK.
keywords: TextResult index, api reference, iOS
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-textresult-index-v9.2.13.html
---

# Barcode Result Classes

## [iTextResult](auxiliary-iTextResult.html)

`iTextResult` is the class that stores the text result data.

```objc
@interface iTextResult
```  

| Attribute | Type | Descriptions |
|-----------|------| ----------- |
| [`barcodeFormat`](auxiliary-iTextResult.html#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](auxiliary-iTextResult.html#barcodeformatstring) | *NSString \** | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](auxiliary-iTextResult.html#barcodeformat_2) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](auxiliary-iTextResult.html#barcodeformatstring_2) | *NSString \** | Barcode type in BarcodeFormat group 2 as string. |
| [`barcodeText`](auxiliary-iTextResult.html#barcodetext) | *NSString \** | The barcode text, ends by '\0'. |
| [`barcodeBytes`](auxiliary-iTextResult.html#barcodebytes) | *NSData \** | The barcode content in a byte array. |
| [`localizationResult`](auxiliary-iTextResult.html#localizationresult) | [`iLocalizationResult`](auxiliary-iLocalizationResult.html) | The corresponding localization result. |
| [`detailedResult`](auxiliary-iTextResult.html#detailedresult) | *NSObject \** | One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.html), [`iPDF417Details`](auxiliary-iPDF417Details.html), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.html), [`iAztecDetails`](auxiliary-iAztecDetails.html), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.html). |
| [`extendedResults`](auxiliary-iTextResult.html#extendedresults) | [`NSArray<iExtendedResult>`](auxiliary-iExtendedResult.html) | The extended result array. |
| [`exception`](auxiliary-iTextResult.html#exception) | *NSString \** | The exception message. |
| [`isDPM`](auxiliary-iTextResult.html#isdpm) | *NSInteger* | This attribute stands for whether the result is a DPM result. |
| [`isMirrored`](auxiliary-iTextResult.html#ismirrored) | *NSInteger* | This attribute stands for whether the barcode is mirrored. |

## [iLocalizationResult](auxiliary-iLocalizationResult.html)

`iLocalizationResult` is the extension of the class [`iTextResult`](auxiliary-iTextResult.html). It stores the localization result information.

```objc
@interface iLocalizationResult
```  

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`terminatePhase`](auxiliary-iLocalizationResult.html#terminatephase) | [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift) | The terminate phase of localization result. |
| [`barcodeFormat`](auxiliary-iLocalizationResult.html#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](auxiliary-iLocalizationResult.html#barcodeformatstring) | *NSString \** | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](auxiliary-iLocalizationResult.html#barcodeformat_2 ) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](auxiliary-iLocalizationResult.html#barcodeformatstring_2) | *NSString \** | Barcode type in BarcodeFormat group 2 as string. |
| [`resultPoints`](auxiliary-iLocalizationResult.html#resultpoints) | *NSArray \** | The vertices coordinates information of the barcode region. |
| [`angle`](auxiliary-iLocalizationResult.html#angle) | *NSInteger* | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](auxiliary-iLocalizationResult.html#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](auxiliary-iLocalizationResult.html#pagenumber) | *NSInteger* | The page number the barcode located in. The index is 0-based. |
| [`regionName`](auxiliary-iLocalizationResult.html#regionname) | *NSString \** | The region name the barcode located in. |
| [`documentName`](auxiliary-iLocalizationResult.html#documentname)| *NSString \** | The document name. |
| [`resultCoordinateType`](auxiliary-iLocalizationResult.html#resultcoordinatetype) | [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift) | The coordinate type. |
| [`accompanyingTextBytes`](auxiliary-iLocalizationResult.html#accompanyingtextbytes) | *NSData \** | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](auxiliary-iLocalizationResult.html#accompanyingtextbyteslength) | *NSInteger* | The length of the accompanying text byte array. |
| [`confidence`](auxiliary-iLocalizationResult.html#confidence) | *NSInteger* | The confidence of the localization result. |

## [iExtendedResult](auxiliary-iExtendedResult.html)

`iExtendedResult` is the extension of the class [`iTextResult`](auxiliary-iTextResult.html). It stores the extended result information.

```objc
@interface iExtendedResult
```  

| Attribute | Type | Descriptions |
|---------- |------|-------------|
| [`resultType`](auxiliary-iExtendedResult.html#resulttype) | [`EnumResultType`]({{ site.mobile_enum }}result-type.html?lang=objc,swift) | The extended result type. |
| [`barcodeFormat`](auxiliary-iExtendedResult.html#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](auxiliary-iExtendedResult.html#barcodeformatstring) | *NSString \** | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](auxiliary-iExtendedResult.html#barcodeformat_2) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](auxiliary-iExtendedResult.html#barcodeformatstring_2) | *NSString \** | Barcode type in BarcodeFormat group 2 as string. |
| [`confidence`](auxiliary-iExtendedResult.html#confidence) | *NSInteger* | The confidence of the result. The higher confidence means the higher accuracy. |
| [`bytes`](auxiliary-iExtendedResult.html#bytes) | *NSData \** | The content in a byte array. |
| [`bytesLength`](auxiliary-iExtendedResult.html#byteslength) | *NSInteger* | The length of the byte array. |
| [`accompanyingTextBytes`](auxiliary-iExtendedResult.html#accompanyingtextbytes) | *NSData \** | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](auxiliary-iExtendedResult.html#accompanyingtextbyteslength) | *NSInteger* | The length of the accompanying text byte array. |
| [`deformation`](auxiliary-iExtendedResult.html#deformation) | *NSInteger* | The deformation value. |
| [`detailedResult`](auxiliary-iExtendedResult.html#detailedresult) | *NSObject \** | One of the following: [`iQRCodeDetails`](auxiliary-iQuadrilateral.html), [`iPDF417Details`](auxiliary-iPDF417Details.html), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.html), [`iAztecDetails`](auxiliary-iAztecDetails.html), [`OneDCodeDetails`](auxiliary-iOneDCodeDetails.html). |
| [`samplingImage`](auxiliary-iExtendedResult.html#samplingimage) | [`iSamplingImageData*`](auxiliary-iSamplingImageData.html) | The sampling image info. |
| [`clarity`](auxiliary-iExtendedResult.html#clarity) | *NSInteger* | The clarity of the barcode zone in percentage. |

## [iAztecDetails](auxiliary-iAztecDetails.html)

`iAztecDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the Aztec code details.

```objc
@interface iAztecDetails
```

| Attribute | Type | Descriptions |
|---------- | -----|------ |
| [`moduleSize`](auxiliary-iAztecDetails.html#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-iAztecDetails.html#rows) | *NSInteger* | The row count of the barcode. |
| [`columns`](auxiliary-iAztecDetails.html#columns) | *NSInteger* | The column count of the barcode. |
| [`layerNumber`](auxiliary-iAztecDetails.html#layernumber) | *NSInteger* | A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code. |

## [iDataMatrixDetails](auxiliary-iDataMatrixDetails.html)

`iDataMatrixDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the DataMatrix code details.

```objc
@interface iDataMatrixDetails
```  

| Attribute | Type | Descriptions |
|---------- |-----|------|
| [`moduleSize`](auxiliary-iDataMatrixDetails.html#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-iDataMatrixDetails.html#rows) | *NSInteger* | The row count of the barcode. |
| [`columns`](auxiliary-iDataMatrixDetails.html#columns) | *NSInteger* | The column count of the barcode. |
| [`dataRegionRows`](auxiliary-iDataMatrixDetails.html#dataregionrows) | *NSInteger* | The data region row count of the barcode. |
| [`dataRegionColumns`](auxiliary-iDataMatrixDetails.html#dataregioncolumns) | *NSInteger* | The data region column count of the barcode. |
| [`dataRegionNumber`](auxiliary-iDataMatrixDetails.html#dataregionnumber) | *NSInteger* | The data region count. |

## [iOneDCodeDetails](auxiliary-iOneDCodeDetails.html)

`iOneDCodeDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the OneD code details.

```objc
@interface iOneDCodeDetails
```  

| Attribute | Type | Descriptions |
|---------- |-----| ---- |
| [`moduleSize`](auxiliary-iOneDCodeDetails.html#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`startCharsBytes`](auxiliary-iOneDCodeDetails.html#startcharsbytes) | *NSData \** | The start chars in a byte array. |
| [`startCharsBytesLength`](auxiliary-iOneDCodeDetails.html#startcharsbyteslength) | *NSInteger* | The length of the start chars byte array. |
| [`stopCharsBytes`](auxiliary-iOneDCodeDetails.html#stopcharsbytes) | *NSData \** | The stop chars in a byte array. |
| [`stopCharsBytesLength`](auxiliary-iOneDCodeDetails.html#stopcharsbyteslength) | *NSInteger* | The length of the stop chars byte array. |
| [`checkDigitBytes`](auxiliary-iOneDCodeDetails.html#checkdigitbytes) | *NSData \** | The check digit chars in a byte array. |
| [`checkDigitBytesLength`](auxiliary-iOneDCodeDetails.html#checkdigitbyteslength) | *NSInteger* | The length of the check digit chars byte array. |

## [iPDF417Details](auxiliary-iPDF417Details.html)

`iPDF417Details` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the PDF417 code details.

```objc
@interface iPDF417Details
```

| Attribute | Type | Descriptions |
|---------- |------|------------ |
| [`moduleSize`](auxiliary-iPDF417Details.html#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](auxiliary-iPDF417Details.html#rows) | *NSInteger* | The row count of the barcode. |
| [`columns`](auxiliary-iPDF417Details.html#columns) | *NSInteger* | The column count of the barcode. |
| [`errorCorrectionLevel`](auxiliary-iPDF417Details.html#errorcorrectionlevel) | *NSInteger* | The error correction level of the barcode. |

## [iQRCodeDetails](auxiliary-iQRCodeDetails.html)

`iQRCodeDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the QRCode details.

```objc
@interface iQRCodeDetails
```  

| Attribute | Type | Descriptions |
|---------- | ---- |-----|
| [`moduleSize`](auxiliary-iQRCodeDetails.html#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixels). |
| [`rows`](auxiliary-iQRCodeDetails.html#rows) | *NSInteger* | The row count of the barcode.   |
| [`columns`](auxiliary-iQRCodeDetails.html#columns) | *NSInteger* | The column count of the barcode. |
| [`errorCorrectionLevel`](auxiliary-iQRCodeDetails.html#errorcorrectionlevel) | *NSInteger* | The error correction level of the barcode.   |
| [`version`](auxiliary-iQRCodeDetails.html#version) | *NSInteger* | The version of the QR Code. |
| [`model`](auxiliary-iQRCodeDetails.html#model) | *NSInteger* | Number of the models. |
| [`mode`](auxiliary-iQRCodeDetails.html#mode) | *NSInteger* | Identify the first data encoding mode. |
| [`page`](auxiliary-iQRCodeDetails.html#page) | *NSInteger* | Identify the position of the particular symbol. |
| [`totalPage`](auxiliary-iQRCodeDetails.html#totalpage) | *NSInteger* | Identify the total number of symbols to be concatenated in the Structured Append format. |
| [`parityData`](auxiliary-iQRCodeDetails.html#paritydata) | *byte* | The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks. |

## [iSamplingImageData](auxiliary-iSamplingImageData.html)

`iSamplingImageData` stores the detailed image data in `iExtendedResult`.

```objc
@interface iSamplingImageData
```  

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`bytes`](auxiliary-iSamplingImageData.html#bytes) | *NSData\** | The sampling image data in a byte array. |
| [`width`](auxiliary-iSamplingImageData.html#width) | *NSInteger* | The width of the sampling image. |
| [`height`](auxiliary-iSamplingImageData.html#height) | *NSInteger* | The height of the sampling image. |
