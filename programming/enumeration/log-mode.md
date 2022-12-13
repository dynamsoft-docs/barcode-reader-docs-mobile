---
layout: default-layout
title: EnumLogMode
description: Use this enum data type to set constants for PDF reading mode of barcodes in Dynamsoft Barcode Reader for JavaScript..
keywords: EnumLogMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumLogMode
permalink: /programming/enumeration/log-mode.html
---


# EnumLogMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumLogMode {
    // Don't save the log.
    public static final int LGM_OFF = 0;
    // Save the log as text.
    public static final int LGM_TEXT = 2;
}
```
>
```objc
typedef NS_ENUM(NSInteger,EnumLogMode)
{
    // Don't save the log.
    EnumLogModeOff = 0x00,
    // Save the log as text.
    EnumLogModeText = 0x02
};
```
>
```swift
public enum EnumLogMode : Int{
    // Don't save the log.
    off = 0x00
    // Save the log as text.
    text = 0x02
}
```
