---
layout: default-layout
title: Dynamsoft Barcode Reader MAUI  API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for MAUI.
keywords: api reference, MAUI
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
---

# SDK Overview: Modules and Main APIs

This page provides an overview of the various modules and highlights the most essential APIs that form the backbone of Dynamsoft Barcode Reader SDKs.

## Modules Summary

**Dynamsoft.BarcodeReaderBundle.Maui** is built on the Dynamsoft Capture Vision (DCV) framework, which includes multiple modules working together to achieve barcode reading. The hierarchical structure diagram below illustrates the various modules of the DBR SDK (with modules at the top depending on those below).

<div align="center">
    <p><img src="../../assets/dcv-dbr-dependency.png" width="70%" alt="region-def"></p>
    <p>Modules hierarchical of the DBR SDK</p>
</div>

The table below describes details the functionalities of these modules:

| File | Description |
|:-----|:------------|
| `Dynamsoft.CaptureVisionRouter.Maui` | The Dynamsoft Capture Vision Router module is the cornerstone of the Dynamsoft Capture Vision (DCV) architecture. It focuses on coordinating batch image processing and provides APIs for setting up image sources and result receivers, configuring workflows with parameters, and controlling processes. |
| `Dynamsoft.BarcodeReader.Maui`(DBR) | The Dynamsoft Barcode Reader module recognizes and decodes multiple barcode formats such as QR codes, Code 39, Code 128, and Data Matrix, among many others. |
| `Dynamsoft.Core.Maui` | The Dynamsoft Core module lays the foundation for Dynamsoft SDKs based on the DCV (Dynamsoft Capture Vision) architecture. It encapsulates the basic classes, interfaces, and enumerations shared by these SDKs.|
| `Dynamsoft.ImageProcessing.Maui` | The Dynamsoft Image Processing module facilitates digital image processing and supports operations for other modules, including the Barcode Reader, Label Recognizer, and Document Normalizer.  |
| `Dynamsoft.License.Maui` | The Dynamsoft License module manages the licensing aspects of Dynamsoft SDKs based on the DCV (Dynamsoft Capture Vision) architecture. |
| `Dynamsoft.CameraEnhancer.Maui` | The Dynamsoft Camera Enhancer (DCE) module controls the camera, transforming it into an image source for the DCV (Dynamsoft Capture Vision) architecture through ISA implementation. It also enhances image quality during acquisition and provides basic viewers for user interaction. |
| `Dynamsoft.Utility.Maui` | The Dynamsoft Utility module defines auxiliary classes, including the ImageManager, and implementations of the CRF (Captured Result Filter) and ISA (Image Source Adapter). These are shared by all Dynamsoft SDKs based on the DCV (Dynamsoft Capture Vision) architecture. |

## Main APIs

### Capture Vision Router

The main class [`CaptureVisionRouter`]({{ site.dcv_maui_api }}capture-vision-router/capture-vision-router.html) acts as the SDK entry point and provides the following essential APIs:

- [Set input]({{ site.dcv_maui_api }}capture-vision-router/multiple-file-processing.html#setinput)
- [Config capture vision settings]({{ site.dcv_maui_api }}capture-vision-router/settings.html)
- [Add result receiver]({{ site.dcv_maui_api }}capture-vision-router/multiple-file-processing.html#addresultreceiver)
- [Start capturing]({{ site.dcv_maui_api }}capture-vision-router/multiple-file-processing.html#startcapturing)

### Image Source Adapter

The [`ImageSourceAdapter`]({{ site.dcv_maui_api }}core/image-source-adapter.html) class is an abstract class representing an adapter for image sources, providing a framework for fetching, buffering, and managing images from various sources. It serves as the input for the [`CaptureVisionRouter`]({{ site.dcv_maui_api }}capture-vision-router/capture-vision-router.html). You can either use the typical implementations of [`ImageSourceAdapter`]({{ site.dcv_maui_api }}core/image-source-adapter.html) or implement your own.

Class [`CameraEnhancer`]({{ site.dce_maui_api }}camera-enhancer.html) is one of the typical implementations of [`ImageSourceAdapter`]({{ site.dcv_maui_api }}core/image-source-adapter.html). It is a class that not only implements the video frame obtaining APIs but also enable you to improve the video quality by adjusting the camera settings.

### Captured Result Receiver

Implement the callback methods of [`CapturedResultReceiver`]({{ site.dcv_maui_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html) to receive the corresponding results you required. The callbacks are triggered when the processing of an image/vide frame is finished or timeout.

#### Barcode Decoding

Callback methods that are related to barcode decoding:

- [`OnDecodedBarcodesReceived`]({{ site.dcv_maui_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#ondecodedbarcodesreceived): The callback of barcode decoding. The result you received in the callback method is a [`DecodedBarcodesResult`]({{ site.dbr_maui_api }}decoded-barcodes-result.html) object, which contains all the decoded barcodes from the processed image.

Related APIs:

- [`DecodedBarcodesResult`]({{ site.dbr_maui_api }}decoded-barcodes-result.html): All barcodes that decoded from the processed image.
- [`BarcodeResultItem`]({{ site.dbr_maui_api }}barcode-result-item.html): The barcode decoding result of a single barcode.

### Camera View

[`CameraView`]({{ site.dce_maui_api }}auxiliary-api/dcecameraview.html) is a view class that design for visualizing the real time video streaming and the barcode decoding result. If the [`CameraEnhancer`]({{ site.dce_maui_api }}camera-enhancer.html) is set as the input of your CVR, the decoded barcodes will be highlighted automatically on the [`CameraView`]({{ site.dce_maui_api }}auxiliary-api/dcecameraview.html).
