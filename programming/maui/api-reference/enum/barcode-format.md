---
layout: default-layout
title: EnumBarcodeFormat - Dynamsoft Barcode Reader MAUI
description: Enumeration EnumBarcodeFormat of DBR MAUI Edition defines the supported barcode formats.
keywords: barcode format, MAUI, OneD, QR Code, GS1 Databar
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumBarcodeFormat
---

# EnumBarcodeFormat

Enumeration `EnumBarcodeFormat` defines the supported barcode formats.

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
namespace Dynamsoft.BarcodeReader.Maui
{
    public enum EnumBarcodeFormat : long
    {
        /** No barcode format specified.*/
        BF_NULL = 0x00,
        /** Represents all supported barcode formats. Useful for scanning operations where any type of barcode is acceptable. */
        BF_ALL = 0xFFFFFFFFFFFFFFFF,
        /** Default barcode formats that are commonly used. This is a subset of `BF_ALL` tailored for general use. */
        BF_DEFAULT = 0xFE3BFFFF,
        /** One-dimensional barcode formats, including BF_CODE_39, BF_CODE_128, BF_CODE_93, BF_CODABAR, BF_ITF, BF_EAN_13, BF_EAN_8, BF_UPC_A, BF_UPC_E, INDUSTRIAL_25, BF_CODE_39_Extended and BF_MSI_CODE. */
        BF_ONED = 0x3007FF,
        /** Code 39 format, widely used in various industries for inventory and manufacturing. */
        BF_CODE_39 = 1L << 0,
        /** Code 128 format, a high-density barcode for alphanumeric or numeric-only data. */
        BF_CODE_128 = 1L << 1,
        /** Code 93 format, similar to Code 39 but more compact and secure with support for the full ASCII character set. */
        BF_CODE_93 = 1L << 2,
        /** Codabar format, used for various numeric barcodes in libraries, blood banks, and parcels. */
        BF_CODABAR = 1L << 3,
        /** Interleaved 2 of 5 format, a numeric-only barcode used in warehousing, distribution, and logistics. */
        BF_ITF = 1L << 4,
        /** EAN-13 format, a superset of the UPC-A barcode used worldwide for marking retail goods. */
        BF_EAN_13 = 1L << 5,
        /** EAN-8 format, a compressed version of EAN-13 for smaller packages. */
        BF_EAN_8 = 1L << 6,
        /** UPC-A format, widely used in the United States and Canada for tracking trade items in stores. */
        BF_UPC_A = 1L << 7,
        /** UPC-E format, a smaller version of the UPC-A barcode used for smaller packages. */
        BF_UPC_E = 1L << 8,
        /** Industrial 2 of 5 format, an older, numeric-only barcode used in the industrial sector. */
        BF_INDUSTRIAL_25 = 1L << 9,
        /** Extended Code 39 format, capable of encoding the full ASCII character set by combining standard Code 39 characters. */
        BF_CODE_39_EXTENDED = 1L << 10,
        /** GS1 DataBar barcode formats, including BF_GS1_DATABAR_OMNIDIRECTIONAL, BF_GS1_DATABAR_TRUNCATED, BF_GS1_DATABAR_STACKED, BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL, BF_GS1_DATABAR_EXPANDED, BF_GS1_DATABAR_EXPANDED_STACKED, BF_GS1_DATABAR_LIMITED. These barcodes are designed for use in retail and healthcare for fresh foods and small items. */
        BF_GS1_DATABAR = 0x3F800,
        BF_GS1_DATABAR_OMNIDIRECTIONAL = 1L << 11,
        BF_GS1_DATABAR_TRUNCATED = 1L << 12,
        BF_GS1_DATABAR_STACKED = 1L << 13,
        BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL = 1L << 14,
        BF_GS1_DATABAR_EXPANDED = 1L << 15,
        BF_GS1_DATABAR_EXPANDED_STACKED = 1L << 16,
        BF_GS1_DATABAR_LIMITED = 1L << 17,
        /** Patch code, a special barcode used for document scanning applications to separate batches of documents. */
        BF_PATCHCODE = 1L << 18,
        /** Micro PDF417, a compact version of PDF417 used for applications where space is limited. */
        BF_MICRO_PDF417 = 1L << 19,
        /** MSI Code, a barcode used in inventory and warehouse to encode information in the distribution of goods. */
        BF_MSI_CODE = 1L << 20,
        /** Code 11, used primarily for labeling telecommunications equipment. */
        BF_CODE_11 = 1L << 21,
        /** Two-Digit Add-On, an extension to UPC and EAN codes for magazines and books. */
        BF_TWO_DIGIT_ADD_ON = 1L << 22,
        /** Five-Digit Add-On, used with UPC and EAN codes for additional data, such as suggested retail price. */
        BF_FIVE_DIGIT_ADD_ON = 1L << 23,
        /** Code 32, also known as Italian PharmaCode, used specifically in the Italian pharmaceutical industry. */
        BF_CODE_32 = 1L << 24,
        /** PDF417, a two-dimensional barcode used in a variety of applications, capable of encoding large amounts of data. */
        BF_PDF417 = 1L << 25,
        /** QR Code, a widely used two-dimensional barcode with high data capacity and error correction capability. */
        BF_QR_CODE = 1L << 26,
        /** DataMatrix, a two-dimensional barcode used for marking small items, providing high data density and reliability. */
        BF_DATAMATRIX = 1L << 27,
        /** Aztec, a two-dimensional barcode known for its compact size and suitability for encoding small amounts of data efficiently. */
        BF_AZTEC = 1L << 28,
        /** MaxiCode, a two-dimensional barcode used primarily for parcel and package tracking in logistics and postal services. */
        BF_MAXICODE = 1L << 29,
        /** Micro QR, a smaller version of the QR Code designed for applications where space is limited. */
        BF_MICRO_QR = 1L << 30,
        /** GS1 Composite, a group of barcodes used in conjunction with GS1 DataBar or linear barcodes to provide additional information. */
        BF_GS1_COMPOSITE = 1L << 31,
        /** Nonstandard barcode, a placeholder for barcodes that do not conform to established industry standards. */
        BF_NONSTANDARD_BARCODE = 1L << 32,
        /** DotCode, a two-dimensional barcode designed for high-speed printing applications. */
        BF_DOTCODE = 1L << 33,
        /** PharmaCode, a general category that includes both BF_PHARMACODE_ONE_TRACK and BF_PHARMACODE_TWO_TRACK. */
        BF_PHARMACODE = 1L << 0xC00000000,
        /** PharmaCode One Track, used in the pharmaceutical industry for packaging control. */
        BF_PHARMACODE_ONE_TRACK = 1L << 34,
        /** PharmaCode Two Track, an extension of PharmaCode for encoding additional data. */
        BF_PHARMACODE_TWO_TRACK = 1L << 35,
        /** Matrix 2 of 5, an older form of barcode used in warehouse sorting and conveyor systems. */
        BF_MATRIX_25 = 1L << 36,
        /** Postal code barcodes, including various formats (BF_USPSINTELLIGENTMAIL, BF_POSTNET, BF_PLANET, BF_AUSTRALIANPOST, BF_RM4SCC and BF_KIX) used by postal services worldwide for efficient mail sorting and delivery. */
        BF_POSTALCODE = 1L << 0x3F0000000000000,
        /** USPS Intelligent Mail, a barcode used by the United States Postal Service to provide greater information and tracking capabilities. */
        BF_USPSINTELLIGENTMAIL = 1L << 52,
        /** Postnet, used by the USPS for automating the sorting of mail. */
        BF_POSTNET = 1L << 53,
        /** Planet, another USPS barcode, similar to Postnet, but with additional data capacity. */
        BF_PLANET = 1L << 54,
        /** Australian Post, barcodes used by the Australian postal service for mail sorting. */
        BF_AUSTRALIANPOST = 1L << 55,
        /** RM4SCC (Royal Mail 4 State Customer Code), used by the UK's Royal Mail for automated mail sorting. */
        BF_RM4SCC = 1L << 56,
        /** KIX (Klant index - Customer index), used by the Dutch postal service for sorting mail. */
        BF_KIX = 1L << 57
    }
}
```
