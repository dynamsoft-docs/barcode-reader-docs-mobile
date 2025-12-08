---
layout: default-layout
title: EnumBarcodeFormat - Dynamsoft Barcode Reader React Native
description: Enumeration EnumBarcodeFormat of DBR React Native Edition defines the supported barcode formats.
keywords: barcode format, React Native, OneD, QR Code, GS1 Databar
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumBarcodeFormat
---

# EnumBarcodeFormat

`EnumBarcodeFormat` is an enumeration that represents the supported barcode formats of the Barcode Reader.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```tsx
const EnumBarcodeFormat = {
    BF_NULL:BigInt(0x00),
    BF_ALL:BigInt(0xFFFFFFFEFFFFFFFFn),
    BF_DEFAULT:BigInt(0xFE3BFFFF),
    BF_ONED:BigInt(0x003007FF),
    BF_GS1_DATABAR:BigInt(0x0003F800),
    BF_CODE_39:BigInt(0x1),
    BF_CODE_128:BigInt(0x2),
    BF_CODE_93:BigInt(0x4),
    BF_CODABAR:BigInt(0x8),
    BF_ITF:BigInt(0x10),
    BF_EAN_13:BigInt(0x20),
    BF_EAN_8:BigInt(0x40),
    BF_UPC_A:BigInt(0x80),
    BF_UPC_E:BigInt(0x100),
    BF_INDUSTRIAL_25:BigInt(0x200),
    BF_CODE_39_EXTENDED:BigInt(0x400),
    BF_GS1_DATABAR_OMNIDIRECTIONAL:BigInt(0x800),
    BF_GS1_DATABAR_TRUNCATED:BigInt(0x1000),
    BF_GS1_DATABAR_STACKED:BigInt(0x2000),
    BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL:BigInt(0x4000),
    BF_GS1_DATABAR_EXPANDED:BigInt(0x8000),
    BF_GS1_DATABAR_EXPANDED_STACKED:BigInt(0x10000),
    BF_GS1_DATABAR_LIMITED:BigInt(0x20000),
    BF_PATCHCODE:BigInt(0x00040000),
    BF_CODE_32:BigInt(0x01000000),
    BF_PDF417:BigInt(0x02000000),
    BF_QR_CODE:BigInt(0x04000000),
    BF_DATAMATRIX:BigInt(0x08000000),
    BF_AZTEC:BigInt(0x10000000),
    BF_MAXICODE:BigInt(0x20000000),
    BF_MICRO_QR:BigInt(0x40000000),
    BF_MICRO_PDF417:BigInt(0x00080000),
    BF_GS1_COMPOSITE:BigInt(0x80000000),
    BF_MSI_CODE:BigInt(0x100000),
    BF_CODE_11:BigInt(0x200000),
    BF_TWO_DIGIT_ADD_ON:BigInt(0x400000),
    BF_FIVE_DIGIT_ADD_ON:BigInt(0x800000),
    BF_MATRIX_25:BigInt(0x1000000000),
    BF_TELEPEN:BigInt(0x2000000000),
    BF_TELEPEN_NUMERIC:BigInt(0x4000000000),
    BF_POSTALCODE:BigInt(0x3F0000000000000),
    BF_NONSTANDARD_BARCODE:BigInt(0x100000000),
    BF_USPSINTELLIGENTMAIL:BigInt(0x10000000000000),
    BF_POSTNET:BigInt(0x20000000000000n),
    BF_PLANET:BigInt(0x40000000000000n),
    BF_AUSTRALIANPOST:BigInt(0x80000000000000n),
    BF_RM4SCC:BigInt(0x100000000000000n),
    BF_KIX:BigInt(0x200000000000000n),
    BF_DOTCODE:BigInt(0x200000000),
    BF_PHARMACODE_ONE_TRACK:BigInt(0x400000000),
    BF_PHARMACODE_TWO_TRACK:BigInt(0x800000000),
    BF_PHARMACODE:BigInt(0xC00000000)
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `none` | No barcode format specified. |
| `all` | Represents all supported barcode formats. Useful for scanning operations where any type of barcode is acceptable. |
| `defaultFormat` | Default barcode formats that are commonly used. This is a subset of `all` tailored for general use. |
| `oned` | One-dimensional barcode formats, including code39, code128, code93, codabar, itf, ean13, ean8, upcA, upcE, industrial25, code39Extended and msiCode. |
| `code39` | Code 39 format, widely used in various industries for inventory and manufacturing. |
| `code128` | Code 128 format, a high-density barcode for alphanumeric or numeric-only data. |
| `code93` | Code 93 format, similar to Code 39 but more compact and secure with support for the full ASCII character set. |
| `codabar` | Codabar format, used for various numeric barcodes in libraries, blood banks, and parcels. |
| `itf` | Interleaved 2 of 5 format, a numeric-only barcode used in warehousing, distribution, and logistics. |
| `ean13` | EAN-13 format, a superset of the UPC-A barcode used worldwide for marking retail goods. |
| `ean8` | EAN-8 format, a compressed version of EAN-13 for smaller packages. |
| `upcA` | UPC-A format, widely used in the United States and Canada for tracking trade items in stores. |
| `upcE` | UPC-E format, a smaller version of the UPC-A barcode used for smaller packages. |
| `industrial25` | Industrial 2 of 5 format, an older, numeric-only barcode used in the industrial sector. |
| `code39Extended` | Extended Code 39 format, capable of encoding the full ASCII character set by combining standard Code 39 characters. |
| `gs1Databar` | GS1 DataBar barcode formats, including gs1DatabarOmnidirectional, gs1DatabarTruncated, gs1DatabarStacked, gs1DatabarStackedOmnidirectional, gs1DatabarExpanded, gs1DatabarExpandedStacked, gs1DatabarLimited. These barcodes are designed for use in retail and healthcare for fresh foods and small items. |
| `gs1DatabarStackedOmnidirectional` | GS1 DataBar Stacked Omnidirectional format. |
| `gs1DatabarTruncated` | GS1 DataBar Truncated format. |
| `gs1DatabarStacked` | GS1 DataBar Stacked format. |
| `gs1DatabarOmnidirectional` | GS1 DataBar Omnidirectional format. |
| `gs1DatabarExpanded` | GS1 DataBar Expanded format. |
| `gs1DatabarExpandedStacked` | GS1 DataBar Expanded Stacked format. |
| `gs1DatabarLimited` | GS1 DataBar Limited format. |
| `patchcode` | Patch code, a special barcode used for document scanning applications to separate batches of documents. |
| `microPdf417` | Micro PDF417, a compact version of PDF417 used for applications where space is limited. |
| `msiCode` | MSI Code, a barcode used in inventory and warehouse to encode information in the distribution of goods. |
| `code11` | Code 11, used primarily for labeling telecommunications equipment. |
| `twoDigitAddOn` | Two-Digit Add-On, an extension to UPC and EAN codes for magazines and books. |
| `fiveDigitAddOn` | Five-Digit Add-On, used with UPC and EAN codes for additional data, such as suggested retail price. |
| `code32` | Code 32, also known as Italian PharmaCode, used specifically in the Italian pharmaceutical industry. |
| `pdf417` | PDF417, a two-dimensional barcode used in a variety of applications, capable of encoding large amounts of data. |
| `qrCode` | QR Code, a widely used two-dimensional barcode with high data capacity and error correction capability. |
| `datamatrix` | DataMatrix, a two-dimensional barcode used for marking small items, providing high data density and reliability. |
| `aztec` | Aztec, a two-dimensional barcode known for its compact size and suitability for encoding small amounts of data efficiently. |
| `maxicode` | MaxiCode, a two-dimensional barcode used primarily for parcel and package tracking in logistics and postal services. |
| `microQr` | Micro QR, a smaller version of the QR Code designed for applications where space is limited. |
| `gs1Composite` | GS1 Composite, a group of barcodes used in conjunction with GS1 DataBar or linear barcodes to provide additional information. |
| `nonStandardBarcode` | Nonstandard barcode, a placeholder for barcodes that do not conform to established industry standards. |
| `dotcode` | DotCode, a two-dimensional barcode designed for high-speed printing applications. |
| `pharmacode` | PharmaCode, a general category that includes both pharmacodeOneTrack and pharmacodeTwoTrack. |
| `pharmacodeOneTrack` | PharmaCode One Track, used in the pharmaceutical industry for packaging control. |
| `pharmacodeTwoTrack` | PharmaCode Two Track, an extension of PharmaCode for encoding additional data. |
| `matrix25` | Matrix 2 of 5, an older form of barcode used in warehouse sorting and conveyor systems. |
| `postalCode` | Combined value of uspsIntelligentMail, postnet, planet, australianPost, rm4scc, kix. |
| `uspsIntelligentMail` | USPS Intelligent Mail, a barcode used by the United States Postal Service to provide greater information and tracking capabilities. |
| `postnet` | Postnet, used by the USPS for automating the sorting of mail. |
| `planet` | Planet, another USPS barcode, similar to Postnet, but with additional data capacity. |
| `australianPost` | Australian Post, barcodes used by the Australian postal service for mail sorting. |
| `rm4scc` | RM4SCC (Royal Mail 4 State Customer Code), used by the UK's Royal Mail for automated mail sorting. |
| `kix` | KIX (Klant index - Customer index), used by the Dutch postal service for sorting mail. |
| `telepen` | Telepen. |
| `telepenNumeric` | Telepen Numeric. A variation of the Telepen format optimized for encoding numeric data only. |
