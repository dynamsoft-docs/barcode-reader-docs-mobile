---
layout: default-layout
title: EnumBarcodeFormat - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumBarcodeFormat of DBR Flutter Edition defines the supported barcode formats.
keywords: barcode format, Flutter, OneD, QR Code, GS1 Databar
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumBarcodeFormat
---

# EnumBarcodeFormat

`EnumBarcodeFormat` is an enumeration that represents the supported barcode formats of the Barcode Reader.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumBarcodeFormat
{
    /** No barcode format specified.**/
    none,
    /** Represents all supported barcode formats. Useful for scanning operations where any type of barcode is acceptable. **/
    all,
    /** Default barcode formats that are commonly used. This is a subset of `all` tailored for general use. **/
    defaultFormat,
    /** One-dimensional barcode formats, including BF_CODE_39, BF_CODE_128, BF_CODE_93, BF_CODABAR, BF_ITF, BF_EAN_13, BF_EAN_8, BF_UPC_A, BF_UPC_E, INDUSTRIAL_25, BF_CODE_39_Extended and BF_MSI_CODE. **/
    oned,
    /** Code 39 format, widely used in various industries for inventory and manufacturing. **/
    code39,
    /** Code 128 format, a high-density barcode for alphanumeric or numeric-only data. **/
    code128,
    /** Code 93 format, similar to Code 39 but more compact and secure with support for the full ASCII character set. **/
    code93,
    /** Codabar format, used for various numeric barcodes in libraries, blood banks, and parcels. **/
    codabar,
    /** Interleaved 2 of 5 format, a numeric-only barcode used in warehousing, distribution, and logistics. **/
    itf,
    /** EAN-13 format, a superset of the UPC-A barcode used worldwide for marking retail goods. **/
    ean13,
    /** EAN-8 format, a compressed version of EAN-13 for smaller packages. **/
    ean8,
    /** UPC-A format, widely used in the United States and Canada for tracking trade items in stores. **/
    upcA,
    /** UPC-E format, a smaller version of the UPC-A barcode used for smaller packages. **/
    upcE,
    /** Industrial 2 of 5 format, an older, numeric-only barcode used in the industrial sector. **/
    industrial25,
    /** Extended Code 39 format, capable of encoding the full ASCII character set by combining standard Code 39 characters. **/
    code39Extended,
    /** GS1 DataBar barcode formats, including BF_GS1_DATABAR_OMNIDIRECTIONAL, BF_GS1_DATABAR_TRUNCATED, BF_GS1_DATABAR_STACKED, BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL, BF_GS1_DATABAR_EXPANDED, BF_GS1_DATABAR_EXPANDED_STACKED, BF_GS1_DATABAR_LIMITED. These barcodes are designed for use in retail and healthcare for fresh foods and small items. **/
    gs1Databar,
    gs1DatabarStackedOmnidirectional,
    gs1DatabarTruncated,
    gs1DatabarStacked,
    gs1DatabarOmnidirectional,
    gs1DatabarExpanded,
    gs1DatabarExpandedStacked,
    gs1DatabarLimited,
    /** Patch code, a special barcode used for document scanning applications to separate batches of documents. **/
    patchcode,
    /** Micro PDF417, a compact version of PDF417 used for applications where space is limited. **/
    microPdf417,
    /** MSI Code, a barcode used in inventory and warehouse to encode information in the distribution of goods. **/
    msiCode,
    /** Code 11, used primarily for labeling telecommunications equipment. **/
    code11,
    /** Two-Digit Add-On, an extension to UPC and EAN codes for magazines and books. **/
    twoDigitAddOn,
    /** Five-Digit Add-On, used with UPC and EAN codes for additional data, such as suggested retail price. **/
    fiveDigitAddOn,
    /** Code 32, also known as Italian PharmaCode, used specifically in the Italian pharmaceutical industry. **/
    code32,
    /** PDF417, a two-dimensional barcode used in a variety of applications, capable of encoding large amounts of data. **/
    pdf417,
    /** QR Code, a widely used two-dimensional barcode with high data capacity and error correction capability. **/
    qrCode,
    /** DataMatrix, a two-dimensional barcode used for marking small items, providing high data density and reliability. **/
    datamatrix,
    /** Aztec, a two-dimensional barcode known for its compact size and suitability for encoding small amounts of data efficiently. **/
    aztec,
    /** MaxiCode, a two-dimensional barcode used primarily for parcel and package tracking in logistics and postal services. **/
    maxicode,
    /** Micro QR, a smaller version of the QR Code designed for applications where space is limited. **/
    microQr,
    /** GS1 Composite, a group of barcodes used in conjunction with GS1 DataBar or linear barcodes to provide additional information. **/
    gs1Composite,
    /** Nonstandard barcode, a placeholder for barcodes that do not conform to established industry standards. **/
    nonStandardBarcode,
    /** DotCode, a two-dimensional barcode designed for high-speed printing applications. **/
    dotcode,
    /** PharmaCode, a general category that includes both BF_PHARMACODE_ONE_TRACK and BF_PHARMACODE_TWO_TRACK. **/
    pharmacode,
    /** PharmaCode One Track, used in the pharmaceutical industry for packaging control. **/
    pharmacodeOneTrack,
    /** PharmaCode Two Track, an extension of PharmaCode for encoding additional data. **/
    pharmacodeTwoTrack,
    /** Matrix 2 of 5, an older form of barcode used in warehouse sorting and conveyor systems. **/
    matrix25,
    /**Combined value of BF2_USPSINTELLIGENTMAIL, BF2_POSTNET, BF2_PLANET, BF2_AUSTRALIANPOST, BF2_RM4SCC, BF_KIX.**/
    postalCode,
    /** USPS Intelligent Mail, a barcode used by the United States Postal Service to provide greater information and tracking capabilities. **/
    uspsIntelligentMail,
    /** Postnet, used by the USPS for automating the sorting of mail. **/
    postnet,
    /** Planet, another USPS barcode, similar to Postnet, but with additional data capacity. **/
    planet,
    /** Australian Post, barcodes used by the Australian postal service for mail sorting. **/
    australianPost,
    /** RM4SCC (Royal Mail 4 State Customer Code), used by the UK's Royal Mail for automated mail sorting. **/
    rm4scc,
    /** KIX (Klant index - Customer index), used by the Dutch postal service for sorting mail. **/
    kix,
    /**Telepen**/
    telepen,
    /**Telepen Numeric. A variation of the Telepen format optimized for encoding numeric data only.**/
    telepenNumeric
}
```
