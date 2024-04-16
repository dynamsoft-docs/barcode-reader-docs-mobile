---
layout: default-layout
title: EnumConflictMode
description: Use this enum data type to set constants for conflict mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumConflictMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumConflictMode
permalink: /programming/enumeration/conflict-mode.html
ignore: true
---


# EnumConflictMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumConflictMode {
    public static final int CM_IGNORE = 1;
    public static final int CM_OVERWRITE = 2;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumConflictMode)
{
    /** Ignores new settings and inherits from previous settings. */
    EnumConflictModeIgnore = 1,
    /** Overwrites and replaces with new settings. */
    EnumConflictModeOverwrite = 2
};
```
>
```swift
public enum EnumConflictMode : Int{
    /** Ignores new settings and inherits from previous settings. */
    ignore = 1
    /** Overwrites and replaces with new settings. */
    overwrite = 2
}
```
