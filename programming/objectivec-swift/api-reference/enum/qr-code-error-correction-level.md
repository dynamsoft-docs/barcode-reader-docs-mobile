---
layout: default-layout
title: QRCodeErrorCorrectionLevel - Dynamsoft Barcode Reader iOS Enumerations
description: The enumeration QRCodeErrorCorrectionLevel of Dynamsoft Barcode Reader iOS describes the error correction level when processing the QR code.
keywords: QR code error correction level
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: QRCodeErrorCorrectionLevel
codeAutoHeight: true
---

# Enumeration QRCodeErrorCorrectionLevel

`QRCodeErrorCorrectionLevel` describes the error correction level when processing the QR code.

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
typedef NS_ENUM(NSInteger, DSQRCodeErrorCorrectionLevel)
{
   /**Error Correction Level H (high) */
   DSQRCodeErrorCorrectionLevelErrorCorrectionH = 0,
   /**Error Correction Level L (low) */
   DSQRCodeErrorCorrectionLevelErrorCorrectionL = 1,
   /**Error Correction Level M (medium-low) */
   DSQRCodeErrorCorrectionLevelErrorCorrectionM = 2,
   /**Error Correction Level Q (medium-high) */
   DSQRCodeErrorCorrectionLevelErrorCorrectionQ = 3
};
```
>
```swift
public enum QRCodeErrorCorrectionLevel : Int
{
   /**Error Correction Level H (high) */
   errorCorrectionH = 0
   /**Error Correction Level L (low) */
   errorCorrectionL = 1
   /**Error Correction Level M (medium-low) */
   errorCorrectionM = 2
   /**Error Correction Level Q (medium-high) */
   errorCorrectionQ = 3
}
```
