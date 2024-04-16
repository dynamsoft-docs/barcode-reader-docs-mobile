---
layout: default-layout
title: EnumIntermediateResultSavingMode
description: Use this enum data type to set constants for intermediate result saving mode of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumIntermediateResultSavingMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumIntermediateResultSavingMode
permalink: /programming/enumeration/intermediate-result-saving-mode.html
ignore: true
---


# EnumIntermediateResultSavingMode

```ts
enum EnumIntermediateResultSavingMode { 
    IRSM_MEMORY = 0x01, 
    IRSM_FILESYSTEM = 0x02, 
    IRSM_BOTH = 0x04 
}
```

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumIntermediateResultSavingMode {
    public static final int IRSM_MEMORY = 1;
    public static final int IRSM_FILESYSTEM = 2;
    public static final int IRSM_BOTH = 4;
    public static final int IRSM_REFERENCE_MEMORY = 8;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumIntermediateResultSavingMode)
{
    /**Saves intermediate results in memory.*/
    EnumIntermediateResultSavingModeMemory = 0x01,
    /**Saves intermediate results in file system. Check @ref IRSM for available argument settings.*/
    EnumIntermediateResultSavingModeFileSystem = 0x02,
    /**Saves intermediate results both in memory and file system. Check @ref IRSM for available argument settings.*/
    EnumIntermediateResultSavingModeBoth = 0x04,
    /**Saves intermediate results in memory with internal data format.*/
    EnumIntermediateResultSavingModeReferenceMemory = 0x08
};
```
>
```swift
public enum EnumIntermediateResultSavingMode : Int{
    /**Saves intermediate results in memory.*/
    memory = 0x01
    /**Saves intermediate results in file system. Check @ref IRSM for available argument settings.*/
    fileSystem = 0x02
    /**Saves intermediate results both in memory and file system. Check @ref IRSM for available argument settings.*/
    both = 0x04
    /**Saves intermediate results in memory with internal data format.*/
    referenceMemory = 0x08
}
```
