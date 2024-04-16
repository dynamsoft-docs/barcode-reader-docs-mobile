---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for Android Language.
keywords: BarcodeReader, api reference, Android
permalink: /programming/android/api-reference/index.html
ignore: true
---

# SDK Overview: Modules and Main APIs

This page provides an overview of the various modules and highlights the most essential APIs that form the backbone of Dynamsoft Barcode Reader SDK.

## Modules Summary

The Dynamsoft Barcode Reader (DBR) SDK is built on the Dynamsoft Capture Vision (DCV) framework, which includes multiple modules working together to achieve barcode reading. The hierarchical structure diagram below illustrates the various modules of the DBR SDK (with modules at the top depending on those below).

<div align="center">
    <p><img src="../../assets/dcv-dbr-dependency.png" width="70%" alt="region-def"></p>
    <p>Modules hierarchical of the DBR SDK</p>
</div>

The table below describes details the functionalities of these modules:

| Module |Description | Mandatory/Optional|
|:--------|:------------|:---|
| `DynamsoftCaptureVisionRouter.aar`(CVR) | Provides APIs for single/multiple images processing, setting configurations, and other features. | Mandatory|
| `DynamsoftBarcodeReader.aar`(DBR) | This library mainly provides barcode decoding algorithms. It includes APIs for you to configure barcode decoding settings and obtaining the barcode results. | Mandatory|
| `DynamsoftCore.aar`(Core) | Provides basic structures and intermediate result related APIs. | Mandatory|
| `DynamsoftImageProcessing.aar`(DIP) | This library mainly provides image processing algorithms. | Mandatory|
| `DynamsoftLicense.aar`(License) | Provides license activation or management APIs. | Mandatory|
| `DynamsoftCameraEnhancer.aar`(DCE) | The <a href="/camera-enhancer/docs/mobile/programming/android/" target="_blank">Dynamsoft Camera Enhancer (DCE) SDK</a> provides camera control, camera enhancements, and basic UI configuration features. | Optional |
| `DynamsoftUtility.aar`(Utility) | The utility library, which includes multiple implementations of image source adapters, result filter, image exporter, and other utility APIs etc.  | Optional |
| `DynamsoftCodeParser.aar`(DCP) | The [Dynamsoft Code Parser (DCP) SDK]({{ site.dcp_android }}){:target="_blank"} for parsing the result. You can use this library for processing the Driver's license or VIN. | Optional |

## Main APIs

### Capture Vision Router

The main class [`CaptureVisionRouter`]({{ site.dcv_android_api }}capture-vision-router/index.html) acts as the SDK entry point and provides the following essential APIs:

- [Set input]({{ site.dcv_android_api }}capture-vision-router/multiple-file-processing.html#setinput)
- [Config barcode reader settings]({{ site.dcv_android_api }}capture-vision-router/settings.html)
- [Add result receiver]({{ site.dcv_android_api }}capture-vision-router/multiple-file-processing.html#addresultreceiver)
- [Start video stream barcode processing]({{ site.dcv_android_api }}capture-vision-router/multiple-file-processing.html#startcapturing)

### Image Source Adapter

The [`ImageSourceAdapter`]({{ site.dcv_android_api }}core/basic-structures/image-souce-adapter.html) class is an abstract class representing an adapter for image sources, providing a framework for fetching, buffering, and managing images from various sources. It serves as the input for the [`CaptureVisionRouter`]({{ site.dcv_android_api }}capture-vision-router/index.html). You can either use the typical implementations of [`ImageSourceAdapter`]({{ site.dcv_android_api }}core/basic-structures/image-souce-adapter.html) or implement your own.

Class [`CameraEnhancer`]({{ site.dce_android }}primary-api/camera-enhancer.html) is one of the typical implementations of [`ImageSourceAdapter`]({{ site.dcv_android_api }}core/basic-structures/image-souce-adapter.html). It is a class that not only implements the video frame obtaining APIs but also enable you to improve the video quality by adjusting the camera settings.

### Captured Result Receiver

To receive the results of video streaming barcode decoding, you need to implement the [`CapturedResultReceiver`](({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html)) with the callback method [`onDecodedBarcodesReceived`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#ondecodedbarcodesreceived). The result you received in the callback method is a [`DecodedBarcodesResult`](decoded-barcodes-result.md) object, which contains all the decoded barcodes from the processed video frame.

- [`onDecodedBarcodesReceived`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#ondecodedbarcodesreceived): The callback method for you to receive the barcode decoding results with a [`DecodedBarcodesResult`](decoded-barcodes-result.md) object.
- [`DecodedBarcodesResult`](decoded-barcodes-result.md): An object that contains all the [`BarcodeResultItem`](barcode-result-item.md) that obtained from a video frame.
- [`BarcodeResultItem`](barcode-result-item.md): The basic item that represents a single barcode with the decoded text and other information.

### Camera View

[`CameraView`]({{ site.dce_android }}auxiliary-api/dcecameraview.html) is a view class that design for visualizing the real time video streaming and the barcode decoding result. If the [`CameraEnhancer`]({{ site.dce_android }}primary-api/camera-enhancer.html) is set as the input of your CVR, the decoded barcodes will be highlighted automatically on the [`CameraView`]({{ site.dce_android }}auxiliary-api/dcecameraview.html).
