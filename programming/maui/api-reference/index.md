---
layout: default-layout
title: Dynamsoft Barcode Reader MAUI API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for MAUI Language.
keywords: BarcodeReader, api reference, MAUI
---

# DBR MAUI Main APIs

## Capture Vision Router

The main class [`CaptureVisionRouter`]({{ site.dcvb_maui_api }}capture-vision-router/capture-vision-router.html) acts as the SDK entry point and provides the following essential APIs:

- [Set input]({{ site.dcvb_maui_api }}capture-vision-router/multiple-file-processing.html#setinput)
- [Config barcode reader settings]({{ site.dcvb_maui_api }}capture-vision-router/settings.html)
- [Add result receiver]({{ site.dcvb_maui_api }}capture-vision-router/multiple-file-processing.html#addresultreceiver)
- [Start video stream barcode processing]({{ site.dcvb_maui_api }}capture-vision-router/multiple-file-processing.html#startcapturing)

## Image Source Adapter

The [`ImageSourceAdapter`]({{ site.dcvb_maui_api }}core/image-source-adapter.html) class is an abstract class representing an adapter for image sources, providing a framework for fetching, buffering, and managing images from various sources. It serves as the input for the [`CaptureVisionRouter`]({{ site.dcvb_maui_api }}capture-vision-router/capture-vision-router.html). You can either use the typical implementations of [`ImageSourceAdapter`]({{ site.dcvb_maui_api }}core/image-source-adapter.html) or implement your own.

Class [`CameraEnhancer`]({{ site.dce_maui_api }}camera-enhancer.html) is one of the typical implementations of [`ImageSourceAdapter`]({{ site.dcvb_maui_api }}core/image-source-adapter.html). It is a class that not only implements the video frame obtaining APIs but also enable you to improve the video quality by adjusting the camera settings.

## Captured Result Receiver

To receive the results of video streaming barcode decoding, you need to implement the [`CapturedResultReceiver`]({{ site.dcvb_maui_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html) with the callback method [`OnDecodedBarcodesReceived`]({{ site.dcvb_maui_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#ondecodedbarcodesreceived). The result you received in the callback method is a [`DecodedBarcodesResult`](decoded-barcodes-result.md) object, which contains all the decoded barcodes from the processed video frame.

- [`OnDecodedBarcodesReceived`]({{ site.dcvb_maui_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#ondecodedbarcodesreceived): The callback method for you to receive the barcode decoding results with a [`DecodedBarcodesResult`](decoded-barcodes-result.md) object.
- [`DecodedBarcodesResult`](decoded-barcodes-result.md): An object that contains all the [`BarcodeResultItem`](barcode-result-item.md) that obtained from a video frame.
- [`BarcodeResultItem`](barcode-result-item.md): The basic item that represents a single barcode with the decoded text and other information.

## Camera View

[`CameraView`]({{ site.dce_maui_api }}camera-view.html) is a view class that design for visualizing the real time video streaming and the barcode decoding result. If the [`CameraEnhancer`]({{ site.dce_maui_api }}camera-enhancer.html) is set as the input of your CVR, the decoded barcodes will be highlighted automatically on the [`CameraView`]({{ site.dce_maui_api }}camera-view.html).
