---
layout: default-layout
title: QRCodeErrorCorrectionLevel - Dynamsoft Barcode Reader Android Enumerations
description: The enumeration QRCodeErrorCorrectionLevel of Dynamsoft Barcode Reader Android describes the error correction level when processing the QR code.
keywords: QR code error correction level
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: QRCodeErrorCorrectionLevel
codeAutoHeight: true
---

# Enumeration QRCodeErrorCorrectionLevel

`QRCodeErrorCorrectionLevel` describes the error correction level when processing the QR code.

```java
@Retention(RetentionPolicy.CLASS)
public @interface EnumQRCodeErrorCorrectionLevel
{
   /**Error Correction Level H (high) */
   public static final int QRECL_ERROR_CORRECTION_H = 0;
   /**Error Correction Level L (low) */
   public static final int QRECL_ERROR_CORRECTION_L = 1;
   /**Error Correction Level M (medium-low) */
   public static final int QRECL_ERROR_CORRECTION_M = 2;
   /**Error Correction Level Q (medium-high) */
   public static final int QRECL_ERROR_CORRECTION_Q = 3;
}
```
