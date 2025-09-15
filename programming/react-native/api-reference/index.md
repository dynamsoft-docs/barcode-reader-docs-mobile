---
layout: default-layout
title: API Reference - Dynamsoft Capture Vision React Native Edition
description: This page is the index of React Native API reference
keywords: API reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: API Index
---

# React Native API Reference

## Classes

| Classes | Description |
| ------- | ----------- |
| [`DCVCameraView`](camera-view.md) | The component class that helps you quickly deploy a camera module and capture video input for barcodes, labels or documents scanning. |
| [`DCVBarcodeReader`](barcode-reader.md) | The functional class that contains barcode decoding related APIs. |

## Interfaces

| Interfaces | Description |
| ---------- | ----------- |
| [`DBRRuntimeSettings`](interface-dbr-runtime-settings.md) | Interface of Barcode settings. |
| [`BarcodeResult`](interface-barcode-result.md) | Interface of barcode results. Barcode result can be acquired from result callback when using video barcode decoding. |
| [`BarcodeLocationResult`](interface-barcode-location-result.md) | The location result of the detected barcodes. |
| [`Quadrilateral`](interface-quadrilateral.md) | The interface that stores the vertex coordinates of a quadrilateral.|
| [`Point`](interface-point.md) | The interface that stores the x and y coordinates of the point. |
| [`Region`](interface-region.md) | The interface of region. Users can configure region of interest. |
| [`Rect`](interface-rect.md) | The interface of rect. |
| [`TorchButton`](interface-torch-button.md) | The interface of torch button. It includes the properities that determines the location, visibility and image of the torch button. |

## Enumerations

| Interfaces | Description |
| ---------- | ----------- |
| [`EnumBarcodeFormat`](enum-barcode-format.md) | The enumeration stores the first group of barcode formats. |
| [`EnumBarcodeFormat_2`](enum-barcode-format2.md) | The enumeration stores the second group of barcode formats. |
| [`EnumDBRPresetTemplate`](enum-dbr-preset-template.md) | The enumeration stores the preset barcode decoding templates. |
| [`EnumTorchState`](enum-torch-state.md) | The enumeration of torch state. |
| [`EnumCameraPosition`](enum-camera-position.md) | The enumeration of torch state. |
