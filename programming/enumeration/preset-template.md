---
layout: default-layout
title: EnumPresetTemplate
description: Use this enum data type to select barcode decoding template in your Dynamsoft Barcode Reader project.
keywords: EnumPresetTemplate, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumPresetTemplate
permalink: /programming/enumeration/preset-template.html
---


# EnumPresetTemplate

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public enum EnumPresetTemplate {
    DEFAULT(0),
    VIDEO_SINGLE_BARCODE(1),
    VIDEO_SPEED_FIRST(2),
    VIDEO_READ_RATE_FIRST(3),
    IMAGE_SPEED_FIRST(4),
    IMAGE_READ_RATE_FIRST(5),
    IMAGE_DEFAULT(6);
}
```
>
```objc
typedef NS_ENUM(NSInteger,EnumPresetTemplate)
{
    /**Default Template.*/
    EnumPresetTemplateDefault = 0,
    /**VideoSingleBarcode Template.*/
    EnumPresetTemplateVideoSingleBarcode = 1,
    /**VideoSpeedFirst Template.*/
    EnumPresetTemplateVideoSpeedFirst = 2,
    /**VideoReadRateFirst Template.*/
    EnumPresetTemplateVideoReadRateFirst = 3,
    /**ImageSpeedFirst Template.*/
    EnumPresetTemplateImageSpeedFirst = 4,
    /**ImageReadRateFirst Template.*/
    EnumPresetTemplateImageReadRateFirst = 5,
    /**ImageDefault Template.*/
    EnumPresetTemplateImageDefault = 6
};
```
>
```swift
public enum EnumPresetTemplate : Int{
    /**Default Template.*/
    default = 0
    /**VideoSingleBarcode Template.*/
    videoSingleBarcode = 1
    /**VideoSpeedFirst Template.*/
    videoSpeedFirst = 2
    /**VideoReadRateFirst Template.*/
    videoReadRateFirst = 3
    /**ImageSpeedFirst Template.*/
    imageSpeedFirst = 4
    /**ImageReadRateFirst Template.*/
    imageReadRateFirst = 5
    /**ImageDefault Template.*/
    imageDefault = 6
}
```
