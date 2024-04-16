---
layout: default-layout
title: EnumTerminatePhase
description: Use this enum data type to set constants for terminate phase of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumTerminatePhase, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumTerminatePhase
permalink: /programming/enumeration/terminate-phase.html
ignore: true
---


# EnumTerminatePhase

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumTerminatePhase {
    public static final int TP_REGION_PREDECTED = 1;
    public static final int TP_IMAGE_PREPROCESSED = 2;
    public static final int TP_IMAGE_BINARIZED = 4;
    public static final int TP_BARCODE_LOCALIZED = 8;
    public static final int TP_BARCODE_TYPE_DETERMINED = 16;
    public static final int TP_BARCODE_RECOGNIZED = 32;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumTerminatePhase)
{
    /** Exits the barcode reading algorithm after the region predetection is done. */
    EnumTerminatePhasePredetected NS_SWIFT_NAME(Predetected) = 0x01,
    /** Exits the barcode reading algorithm after the region predetection and image pre-processing is done. */
    EnumTerminatePhasePreprocecessed NS_SWIFT_NAME(Preprocecessed) = 0x02,
    /** Exits the barcode reading algorithm after the region predetection, image pre-processing, and image binarization are done. */
    EnumTerminatePhaseBinarized NS_SWIFT_NAME(Binarized) = 0x04,
    /** Exits the barcode reading algorithm after the region predetection, image pre-processing, image binarization, and barcode localization are done. */
    EnumTerminatePhaseLocalized NS_SWIFT_NAME(Localized) = 0x08,
    /** Exits the barcode reading algorithm after the region predetection, image pre-processing, image binarization, barcode localization, and barcode type determining are done. */
    EnumTerminatePhaseDetermined NS_SWIFT_NAME(Determined) = 0x10,
    /** Exits the barcode reading algorithm after the region predetection, image pre-processing, image binarization, barcode localization, barcode type determining, and barcode recognition are done. */
    EnumTerminatePhaseRecognized NS_SWIFT_NAME(Recognized) = 0x20
};
```
>
```swift
public enum EnumTerminatePhase : Int{
    /** Exits the barcode reading algorithm after the region predetection is done. */
    Predetected = 0x01
    /** Exits the barcode reading algorithm after the region predetection and image pre-processing is done. */
    Preprocecessed = 0x02
    /** Exits the barcode reading algorithm after the region predetection, image pre-processing, and image binarization are done. */
    Binarized = 0x04
    /** Exits the barcode reading algorithm after the region predetection, image pre-processing, image binarization, and barcode localization are done. */
    Localized = 0x08
    /** Exits the barcode reading algorithm after the region predetection, image pre-processing, image binarization, barcode localization, and barcode type determining are done. */
    Determined = 0x10
    /** Exits the barcode reading algorithm after the region predetection, image pre-processing, image binarization, barcode localization, barcode type determining, and barcode recognition are done. */
    Recognized = 0x20
}
```
