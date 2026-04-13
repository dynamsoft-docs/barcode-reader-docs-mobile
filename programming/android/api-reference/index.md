---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Main Page
description: Main API reference page for Dynamsoft Barcode Reader SDK for Android.
keywords: BarcodeReader, api reference, Android
---

# SDK Overview: Modules and Main APIs

This page summarizes the SDK modules and core APIs of Dynamsoft Barcode Reader.

## Modules Summary

Dynamsoft Barcode Reader (DBR) SDK is built on the Dynamsoft Capture Vision (DCV) architecture.

<style>
  svg {
    max-width: 100%;
    height: auto;
  }

  .clickable {
    fill: transparent;
    cursor: pointer;
  }

  .clickable:hover {
    fill: rgba(0, 123, 255, 0.2);
    stroke: #007bff;
    stroke-width: 2;
  }
</style>
<svg viewBox="0 0 1397 768">
  <image href="../../assets/architecture-cvr.png" width="1397" height="768"/>
  <a href="{{ site.dce_android }}primary-api/camera-enhancer.html">
    <rect class="clickable"
          x="110" y="310"
          width="305" height="180" />
  </a>
  <a href="{{ site.dcvb_android_api }}capture-vision-router/capture-vision-router.html">
    <rect class="clickable"
          x="500" y="350"
          width="370" height="105" />
  </a>
  <a href="{{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html">
    <rect class="clickable"
          x="970" y="310"
          width="330" height="230" />
  </a>
  <a href="{{ site.dbr_android_api }}">
    <rect class="clickable"
          x="480" y="570"
          width="210" height="150" />
  </a>
  <a href="{{ site.dcp_android_api }}code-parser.html">
    <rect class="clickable"
          x="700" y="570"
          width="210" height="150" />
  </a>
  <a href="{{ site.dcvb_android_api }}capture-vision-router/settings.html">
    <rect class="clickable"
          x="510" y="60"
          width="320" height="200" />
  </a>
</svg>

## Main APIs

| Category | Library | Description |
| -------- | --- | ----------- |
| Orchestration | DynamsoftCaptureVisionRouter | Core Capture Vision Router APIs for configuring settings, starting or stopping capture, and registering receivers. |
| Functional Modules | DynamsoftBarcodeReader<br>DynamsoftCodeParser | APIs for functional modules, mainly for decoded results and result processing. |
| Input & UI Enhancement | DynamsoftCameraEnhancer | APIs for camera control, image enhancement, and camera UI. |
| Infrastructure & Utility | DynamsoftLicense<br>DynamsoftCore<br>DynamsoftUtility | Licensing, basic structures, intermediate results, and utility APIs. |

### Capture Vision Router

The main class [`CaptureVisionRouter`]({{ site.dcvb_android_api }}capture-vision-router/capture-vision-router.html) acts as the SDK entry point and provides the following essential APIs:

- [Set input]({{ site.dcvb_android_api }}capture-vision-router/multiple-file-processing.html#setinput)
- [Configure barcode reader settings]({{ site.dcvb_android_api }}capture-vision-router/settings.html)
- [Add result receiver]({{ site.dcvb_android_api }}capture-vision-router/multiple-file-processing.html#addresultreceiver)
- [Start barcode capture from a video stream]({{ site.dcvb_android_api }}capture-vision-router/multiple-file-processing.html#startcapturing)

### Image Source

Implement [`ImageSourceAdapter`]({{ site.dcvb_android_api }}core/basic-structures/image-source-adapter.html) and bind it to [`CaptureVisionRouter`]({{ site.dcvb_android_api }}capture-vision-router/capture-vision-router.html) so the SDK can continuously receive images.

Built-in implementations include:

- [`CameraEnhancer`]({{ site.dce_android }}primary-api/camera-enhancer.html) for video streams. [`CameraView`]({{ site.dce_android }}auxiliary-api/dcecameraview.html) provides the corresponding camera UI.
- [`DirectoryFetcher`]({{ site.dcvb_android_api }}utility/directory-fetcher.html) for files or folders.

### Result

#### Receiver and Callbacks

Implement [`CapturedResultReceiver`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html) to receive capture results.

| Callback | Description |
| -------- | ----------- |
| [`onDecodedBarcodesReceived`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#ondecodedbarcodesreceived) | Callback for receiving barcode decoding results as a [`DecodedBarcodesResult`](decoded-barcodes-result.md) object. |
| [`onParsedResultReceived`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#onparsedresultreceived) | Callback for receiving parsed results as a [`ParsedResult`]({{ site.dcp_android_api }}parsed-result.html) object. |
| [`onCapturedResultReceived`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#oncapturedresultreceived) | Callback for receiving all result types as a [`CapturedResult`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result.html) object. |

#### Result Objects

| Result | Basic Item | Type |
| ------ | ---------- | ---- |
| [`CapturedResult`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result.html) | [`CapturedResultItem`]({{ site.dcvb_android_api }}core/basic-structures/captured-result-item.html) | Depends on `CapturedResultItemType`. Cast items to the corresponding subclass before use. |
| [`DecodedBarcodesResult`](decoded-barcodes-result.md) | [`BarcodeResultItem`](barcode-result-item.md) | `CRIT_BARCODE` |
| [`ParsedResult`]({{ site.dcp_android_api }}parsed-result.html) | [`ParsedResultItem`]({{ site.dcp_android_api }}parsed-result-item.html) | `CRIT_PARSED_RESULT` |
