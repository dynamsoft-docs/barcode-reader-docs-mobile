---
layout: default-layout
title: How to use AVCaptureSession or Third-party Camera Modules with Dynamsoft Barcode Reader?
keywords: Dynamsoft Barcode Reader, FAQ, Mobile, tech basic, android, requirements
description: How to use AVCaptureSession or Third-party Camera Modules with Dynamsoft Barcode Reader?
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/android/faq/no-camera-enhancer-v9.6.30.html
---

# How to use AVCaptureSession or Third-party Camera Modules with Dynamsoft Barcode Reader?

[<< Back to FAQ index](index.md)


You can read this [article](../samples/no-camera-enhancer.md) for how to decode barcodes from AVCaptureSession or directly view this <a href="https://www.dynamsoft.com/barcode-reader/docs/mobile/programming/android/api-reference/primary-decode.html?ver=latest#get-imagedata-from-android-camera2" target="_blank">code snippet sample</a>. 

> **_NOTE:_** Decode barcodes from an `ImageData` object. The `ImageData` object stores the pixel buffer, width, height, stride and pixel format of the image. However, it is always recommended to use DBR in conjunction with DCE for the best results and performance.