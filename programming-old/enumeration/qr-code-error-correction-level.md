---
layout: default-layout
title: EnumQRCodeErrorCorrectionLevel
description: Use this enum data type to set constants for QR code error correction level of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumQRCodeErrorCorrectionLevel, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumQRCodeErrorCorrectionLevel
permalink: /programming/enumeration/qr-code-error-correction-level.html
ignore: true
---


# EnumQRCodeErrorCorrectionLevel

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumQRCodeErrorCorrectionLevel {
    public static final int QRECL_ERROR_CORRECTION_H = 0;
    public static final int QRECL_ERROR_CORRECTION_L = 1;
    public static final int QRECL_ERROR_CORRECTION_M = 2;
    public static final int QRECL_ERROR_CORRECTION_Q = 3;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumQRCodeErrorCorrectionLevel)
{
    /** Error Correction Level H (high) */
    EnumQRCodeErrorCorrectionLevelErrorCorrectionH = 0,
    /** Error Correction Level L (low) */
    EnumQRCodeErrorCorrectionLevelErrorCorrectionL = 1,
    /** Error Correction Level M (medium-low) */
    EnumQRCodeErrorCorrectionLevelErrorCorrectionM = 2,
    /** Error Correction Level Q (medium-high) */
    EnumQRCodeErrorCorrectionLevelErrorCorrectionQ = 3
};
```
>
```swift
public enum EnumQRCodeErrorCorrectionLevel : Int{
    /** Error Correction Level H (high) */
    errorCorrectionH = 0
    /** Error Correction Level L (low) */
    errorCorrectionL = 1
    /** Error Correction Level M (medium-low) */
    errorCorrectionM = 2
    /** Error Correction Level Q (medium-high) */
    errorCorrectionQ = 3
}
```
