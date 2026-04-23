---
layout: default-layout
title: Camera Control - Dynamsoft Barcode Reader iOS
description: Learn how to control the camera for Dynamsoft Barcode Reader iOS, including focus behavior, zoom and related enhancement features.
keywords: camera, iOS, auto-zoom, zoom, focus
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Camera Control

This page introduces the main camera control features available in Dynamsoft Barcode Reader for iOS. It explains how to manage focus behavior, configure zoom for small or distant barcodes, and use the available camera enhancement features to improve scanning performance in specific scenarios.

## Focus Control & Focus Modes

In most cases, the camera automatically determines when focus is needed and adjusts the focal length accordingly. This behavior is called continuous auto-focus. In addition, the camera view supports tap-to-focus, which allows the user to trigger auto-focus manually.

If your workflow needs to react to focus completion, you can register a focus listener on `DSCameraEnhancer`.

**Related API**

- [`setFocusListener`]({{ site.dce_ios_api }}primary-api/camera-enhancer.html#setfocuslistener)
- [`FocusListener`]({{ site.dce_ios_api }}auxiliary-api/interface-focus-listener.html)

## Auto-Zoom & Zoom Factor

Zoom control is commonly used when processing small barcodes or scanning from a long distance. There are two zoom control features:

- Auto-zoom: Lets the library determine whether to zoom in.
- Zoom factor: Lets you set the zoom factor directly. This is commonly used when focusing on small barcodes.

For detailed setup instructions and code examples, see [Zoom Control](zoom-control.md).

## Enhanced Features

When your workflow includes challenging camera conditions, use `DSCameraEnhancer` enhancement features together with barcode-scanning settings to improve the overall experience.

- Auto zoom helps recognize distant barcodes.
- Focus-related callbacks let you coordinate your UI with camera focus events.
- BarcodeScanner configuration can also be used when you want to control zoom directly in the ready-to-use flow.

**Related APIs**

- [`enableEnhancedFeatures`]({{ site.dce_ios }}primary-api/camera-enhancer.html#enableenhancedfeatures)
- [`setZoomFactor`]({{ site.dce_ios }}primary-api/camera-enhancer.html#setzoomfactor)
- [`zoomFactor`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#zoomfactor)
- [`isAutoZoomEnabled`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#isautozoomenabled)