---
layout: default-layout
title: EnumTextResultOrderMode
description: Use this enum data type to set constants for text result order mode of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumTextResultOrderMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumTextResultOrderMode
permalink: /programming/enumeration/text-result-order-mode.html
ignore: true
---


# EnumTextResultOrderMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumTextResultOrderMode {
    public static final int TROM_CONFIDENCE = 1;
    public static final int TROM_POSITION = 2;
    public static final int TROM_FORMAT = 4;
    public static final int TROM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumTextResultOrderMode)
{
    /** Returns the text results in descending order by confidence. */
    EnumTextResultOrderModeConfidence = 0x01,
    /** Returns the text results in position order, from top to bottom, then left to right */
    EnumTextResultOrderModePosition = 0x02,
    /** Returns the text results in alphabetical and numerical order by barcode format string. */
    EnumTextResultOrderModeFormat = 0x04,
    /** Skips the ordering operation. */
    EnumTextResultOrderModeSkip = 0x00
};
```
>
```swift
public enum EnumTextResultOrderMode : Int{
    /** Returns the text results in descending order by confidence. */
    confidence = 0x01
    /** Returns the text results in position order, from top to bottom, then left to right */
    position = 0x02
    /** Returns the text results in alphabetical and numerical order by barcode format string. */
    format = 0x04
    /** Skips the ordering operation. */
    skip = 0x00
}
```
