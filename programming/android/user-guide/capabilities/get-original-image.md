---
layout: default-layout
title: Get Original Image - Dynamsoft Barcode Reader Android
description: Learn how to get the original image that produces the current result in the Dynamsoft Barcode Reader Android SDK.
keywords: original image, Android, java, kotlin
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Get Original Image

> [!Important]
> Features on this page are only available for the **Foundational APIs**.

## Get by HashId (Recommended)

Keep your current result output logic unchanged. Use `originalImageHashId` from `DecodedBarcodesResult` to fetch the original image only when needed.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
public void onDecodedBarcodesReceived(@NonNull DecodedBarcodesResult result) {
  ImageData originalImage = mRouter.getIntermediateResultManager().getOriginalImage(result.getOriginalImageHashId());
}
```
2. 
```kotlin
override fun onDecodedBarcodesReceived(result: DecodedBarcodesResult) {
   val originalImage = mRouter.intermediateResultManager.getOriginalImage(result.originalImageHashId)
}
```

- [`getOriginalImageHashId`]({{ site.dbr_android_api }}decoded-barcodes-result.html)
- [`getIntermediateResultManager`]({{ site.dcvb_android_api }}capture-vision-router/intermediate-result.html#getintermediateresultmanager)
- [`getOriginalImage`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html#getoriginalimage)

## Include Original Image in Results

Enable original image output in settings so each capture result can directly contain the original image item. This is convenient for downstream processing, but usually adds more data to each result.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
try { 
   SimplifiedCaptureVisionSettings settings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   // Set the outputOriginalImage to true so that the original image will be included in the CapturedResultReceiver.
   settings.outputOriginalImage = true;
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, settings);
} catch (CaptureVisionRouterException e) {
   throw new RuntimeException(e);
}
mRouter.addResultReceiver(new CapturedResultReceiver() {
   @Override
   public void onCapturedResultReceived(@NonNull CapturedResult result) {
          if (result.getItems().length>1)
          {
             for(CapturedResultItem item:result.getItems())
             {
                    if (item.getType() == EnumCapturedResultItemType.CRIT_BARCODE)
                    {
                       // Use barcode result
                    }else if (item.getType() == EnumCapturedResultItemType.CRIT_ORIGINAL_IMAGE)
                    {
                       // USe original image
                    }
             }
          }
   }
});
```
2. 
```kotlin
try {
   val settings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES)
   // Set outputOriginalImage to true so that the original image will be included in CapturedResultReceiver.
   settings.outputOriginalImage = true
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, settings)
} catch (e: CaptureVisionRouterException) {
   throw RuntimeException(e)
}
mRouter.addResultReceiver(object : CapturedResultReceiver {
   override fun onCapturedResultReceived(result: CapturedResult) {
          if (result.items.size > 1) {
             for (item in result.items) {
                    if (item.type == EnumCapturedResultItemType.CRIT_BARCODE) {
                       // Use barcode result
                    } else if (item.type == EnumCapturedResultItemType.CRIT_ORIGINAL_IMAGE) {
                       // Use original image
                    }
             }
          }
   }
})
```

- [`outputOriginalImage`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#outputoriginalimage)
- [`onCapturedResultReceived`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#oncapturedresultreceived)
