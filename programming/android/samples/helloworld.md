---
layout: default-layout
title: HelloWorld Sample - Dynamsoft Barcode Reader for Android
description: This is the HelloWorld Sample page of Dynamsoft Barcode Reader for Android SDK.
keywords: android, samples, HelloWorld
needAutoGenerateSidebar: true
breadcrumbText: HelloWorld
permalink: /programming/android/samples/helloworld.html
---

# Decode from Video Sample - Use DynamsoftCameraEnhancer as Image Source

This sample illustrates how to recognize barcodes from the video streaming. In this sample, you can read how to use [`DynamsoftCameraEnhancer`]({{ site.dce_ios }}) to capture the video streaming.

**View the sample code**

* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/HelloWorld/DecodeWithCameraEnhancer/" target="_blank">Java HelloWorld Sample</a>
* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/HelloWorld/DecodeWithCameraEnhancerKt/" target="_blank">Kotlin HelloWorld Sample</a>

There are some basic concepts that are helpful on understanding the SDK.

## CaptureVisionRouter

[`CaptureVisionRouter`]({{ site.dcv_android_api }}capture-vision-router/capture-vision-router.html) is a router that responsible for retrieving images from the source, coordinating the image processing tasks and dispatching the processing results. To implement a barcode decoding task, what you have to do are:

* Set a standard input for your `CaptureVisionRouter` instance.
* Set a result receiver via your `CaptureVisionRouter` instance.
* Tell your `CaptureVisionRouter` instance to start working and specify a barcode decoding template with its name.
* (Additional) Configure the image processing Parameters to optimize the barcode decoding performance.

## Standard Input

Use the [`setInput`]({{ site.dcv_android_api }}capture-vision-router/multiple-file-processing.html#setinput) method of the `CaptureVisionRouter` to bind an `ImageSourceAdapter` (ISA) instance is the simplest way to access to the standard input. `CameraEnhancer` is one of the official implementation of the ISA for you to quickly set up the mobile camera as the image source.

## Output

To get the output result, you have to implement the `CapturedResultReceiver` and bind it with your `CaptureVisionRouter` instance. You will receive the barcode decoding results in the [`onDecodedBarcodesReceived`]({{ site.dcv_android_api }}core/basic-structures/captured-result-receiver.html#ondecodedbarcodesreceived) method each time when a image (video frame) is processed.

## Control the Start & Stop of the Capturing

If only one barcode decoding result is required in one scan, you can stop the barcode decoding thread via [`stopCapturing`]({{ site.dcv_android_api }}capture-vision-router/multiple-file-processing.html#stopcapturing) method. You can call the [`startCapturing`]({{ site.dcv_android_api }}capture-vision-router/multiple-file-processing.html#startcapturing) at any time when you want to restart the barcode decoding.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
@Override
public void (DecodedBarcodesResult result) {
    if (result != null && result.getItems() != null && result.getItems().length > 0){
        runOnUiThread(() -> mRouter.stopCapturing());
    }
}
```
2. 
```kotlin
override fun onDecodedBarcodesReceived(result: DecodedBarcodesResult) {
    if (result?.items != null && result.items.isNotEmpty()) {
        runOnUiThread { mRouter.stopCapturing() }
    }
}
```
