---
layout: default-layout
title: ExtendedBarcodeResultType - Dynamsoft Barcode Reader iOS Enumerations
description: The enumeration ExtendedBarcodeResultType of Dynamsoft Barcode Reader iOS describes the type of the extended barcode result.
keywords: Extended barcode result type
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: ExtendedBarcodeResultType
codeAutoHeight: true
---

# Enumeration ExtendedBarcodeResultType

`ExtendedBarcodeResultType` determines the type of text result returned from a barcode scan.

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
typedef NS_ENUM(NSInteger, DSExtendedBarcodeResultType)
{
   /**Specifies the standard text. This means the barcode value. */
   DSExtendedBarcodeResultTypeStandardResult = 0,
   /**Specifies all the candidate text. This means all the standard text results decoded from the barcode. */
   DSExtendedBarcodeResultTypeCandidateResult = 1,
   /**Specifies the partial text. This means part of the text result decoded from the barcode. */
   DSExtendedBarcodeResultTypePartialResult = 2
};
```
>
```swift
public enum ExtendedBarcodeResultType : Int
{
   /**Specifies the standard text. This means the barcode value. */
   standardResult = 0
   /**Specifies all the candidate text. This means all the standard text results decoded from the barcode. */
   candidateResult = 1
   /**Specifies the partial text. This means part of the text result decoded from the barcode. */
   partialResult = 2
}
```
