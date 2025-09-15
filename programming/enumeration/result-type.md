---
layout: default-layout
title: EnumResultType
description: Use this enum data type to set constants for the result type of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumResultType, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumResultType
permalink: /programming/enumeration/result-type.html
ignore: true
---


# EnumResultType

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumResultType {
    public static final int RT_STANDARDTEXT = 0;
    public static final int RT_RAWTEXT = 1;
    public static final int RT_CANDIDATETEXt = 2;
    public static final int RT_PARTIALTEXT = 3;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumResultType)
{
    /** Specifies the standard text. This means the barcode value. */
    EnumResultTypeStandardText = 0,
    /** Specifies the raw text. This means the text that includes start/stop characters, check digits, etc. */
    EnumResultTypeRawText = 1,
    /** Specifies all the candidate text. This means all the standard text results decoded from the barcode. */
    EnumResultTypeCandidateText = 2,
    /** Specifies the partial text. This means part of the text result decoded from the barcode. */
    EnumResultTypePartialText = 3
};
```
>
```swift
public enum EnumResultType : Int{
    /** Specifies the standard text. This means the barcode value. */
    standardText = 0
    /** Specifies the raw text. This means the text that includes start/stop characters, check digits, etc. */
    rawText = 1
    /** Specifies all the candidate text. This means all the standard text results decoded from the barcode. */
    candidateText = 2
    /** Specifies the partial text. This means part of the text result decoded from the barcode. */
    partialText = 3
}
```
