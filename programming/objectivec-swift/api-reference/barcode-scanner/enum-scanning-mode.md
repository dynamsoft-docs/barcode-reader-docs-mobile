---
layout: default-layout
title: DSScanningMode - Dynamsoft Barcode Reader iOS Edition
description: DSScanningMode of Dynamsoft Barcode Reader iOS is an enumeration class that defines the barcode scanning mode.
keywords: scan modes, scanning modes, single, multiple barcodes
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSScanningMode
---

# DSScanningMode

`DSScanningMode` is an enumeration class that defines the barcode scanning mode.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
typedef NS_ENUM(NSInteger, DSScanningMode)
{
    /**
     * The scan mode for scanning single barcode.
     */
    DSScanningModeSingle,
    /**
     * The scan mode for scanning multiple barcodes.
     */
    DSScanningModeMultiple
};
```
1. 
```swift
@objc public enum ScanningMode: Int {
    /**
     * The scan mode for scanning single barcode.
     */
    case single
    /**
     * The scan mode for scanning multiple barcodes.
     */
    case multiple
}
```
