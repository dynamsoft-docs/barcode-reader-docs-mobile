---
layout: default-layout
title: Dynamsoft Barcode Reader Flutter API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for Flutter.
keywords: api reference, Flutter, barcode reader
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
---

# Capture Vision SDK Overview: Modules and Main APIs

This page provides an overview of the various modules and highlights the most essential APIs that form Dynamsoft Capture Vision, the backbone of Dynamsoft Barcode Reader SDKs.

## API Overview

### Capture Vision Router

The Dynamsoft Capture Vision Router class is the cornerstone of the Dynamsoft Capture Vision (DCV) architecture. It focuses on coordinating batch image processing and provides API for setting up image sources and result receivers, configuring workflows with parameters, and controlling processes. Dynamsoft Capture Vision helps connects the functional products of Dynamsoft under the same umbrella - allowing for easier integration and interchangeable API to control them all.

You can find the CaptureVisionRouter API [here]({{ site.dcv_flutter_api }}capture-vision-router/capture-vision-router.html).

This guide focuses on the Barcode Reader functional product. To learn how to use the foundational Capture Vision API to set up and run the Barcode Reader, please refer to the [User Guide (Foundational Edition)]({{ site.dbr_flutter }}foundational-user-guide.html).

### Image Source

[`CameraEnhancer`]({{ site.dce_flutter_api }}primary-api/camera-enhancer.html) is a class that not only implements the video frame obtaining APIs but also enable you to improve the video quality by adjusting the camera settings.

### Captured Result Receiver

To receive the results of video streaming barcode decoding, you need to implement the [`CapturedResultReceiver`]({{ site.dcv_flutter_api }}capture-vision-router/captured-result-receiver.html) with the callback method [`onDecodedBarcodesReceived`]({{ site.dcv_flutter_api }}capture-vision-router/captured-result-receiver.html#ondecodedbarcodesreceived). The result you received in the callback method is a [`DecodedBarcodesResult`](barcode-reader/decoded-barcodes-result.md) object, which contains all the decoded barcodes from the processed video frame.

- [`onDecodedBarcodesReceived`]({{ site.dcv_flutter_api }}capture-vision-router/captured-result-receiver.html#ondecodedbarcodesreceived): The callback method for you to receive the barcode decoding results with a [`DecodedBarcodesResult`](barcode-reader/decoded-barcodes-result.md) object.
- [`DecodedBarcodesResult`](barcode-reader/decoded-barcodes-result.md): An object that contains all the [`BarcodeResultItem`](barcode-reader/barcode-result-item.md) that obtained from a video frame.
- [`BarcodeResultItem`](barcode-reader/barcode-result-item.md): The basic item that represents a single barcode with the decoded text and other information.

### Camera View

[`CameraView`]({{ site.dce_flutter_api }}camera-view.html) is a view class that design for visualizing the real time video streaming and the barcode decoding result. If the [`CameraEnhancer`]({{ site.dce_flutter_api }}camera-enhancer.html) is set as the input of your CVR, the decoded barcodes will be highlighted automatically on the [`CameraView`]({{ site.dce_flutter_api }}camera-view.html).
