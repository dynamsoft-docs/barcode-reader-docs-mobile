---
layout: default-layout
title: ExtendedBarcodeResultType - Dynamsoft Barcode Reader Android Enumerations
description: The enumeration ExtendedBarcodeResultType of Dynamsoft Barcode Reader Android describes the type of the extended barcode result.
keywords: Extended barcode result type
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: ExtendedBarcodeResultType
codeAutoHeight: true
---

# Enumeration ExtendedBarcodeResultType

`ExtendedBarcodeResultType` determines the type of text result returned from a barcode scan.

```java
@Retention(RetentionPolicy.CLASS)
public @interface EnumExtendedBarcodeResultType
{
   /**Specifies the standard text. This means the barcode value. */
   public static final int EBRT_STANDARD_RESULT = 0;
   /**Specifies all the candidate text. This means all the standard text results decoded from the barcode. */
   public static final int EBRT_CANDIDATE_RESULT = 1;
   /**Specifies the partial text. This means part of the text result decoded from the barcode. */
   public static final int EBRT_PARTIAL_RESULT = 2;
}
```
