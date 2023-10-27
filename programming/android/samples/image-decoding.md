---
layout: default-layout
title: DecodeFromAnImage Sample - Dynamsoft Barcode Reader for Android
description: This is the page of DecodeFromAnImage sample of Dynamsoft Barcode Reader for Android SDK.
keywords: android, samples, decode from an image
needAutoGenerateSidebar: true
breadcrumbText: DecodeFromAnImage
permalink: /programming/android/samples/image-decoding.html
---

# Decode From an Image Sample

`DecodeFromAnImage` sample shows how to pick an image from system album and decode the image.

**View the sample code**

* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/HelloWorld/DecodeFromAnImage/" target="_blank">Java Decode from an Image Sample</a>
* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/HelloWorld/DecodeFromAnImageKt/" target="_blank">Kotlin Decode from an Image Sample</a>

In the sample, you can see how to read an image from the album as a `Bitmap` and use [`capture(bitmap,templateName)`]({{ site.dcv_android_api }}capture-vision-router/single-file-processing.html#capturebitmaptemplatename) method to process the Bitmap.

The following `capture` methods are also available to process the other image types.

* [`capture(filePath,templateName)`]({{ site.dcv_android_api }}capture-vision-router/single-file-processing.html#capturefilepathtemplatename): Process an image file with a file path.
* [`capture(fileBytes,templateName)`]({{ site.dcv_android_api }}capture-vision-router/single-file-processing.html#capturefilebytestemplatename): Process an image file in memory.
* [`capture(imageData,templateName)`]({{ site.dcv_android_api }}capture-vision-router/single-file-processing.html#captureimagedatatemplatename): Process an [`ImageData`]({{ site.dcv_android_api }}core/basic-structures/image-data.html).

When triggering the `capture` methods, a template name is required. You can use the enumeration `PresetTemplate` to specify one of the preset templates or input the name of your customized template. Barcode decoding preset templates are available as follow:

* readBarcodes: The default barcode decoding template. It is speed-first and only read one barcode from an single image.
* readBarcodesSpeedFirst: The speed-first barcode decoding template. Different from the default template, this template can read multiple barcodes at once.
* readBarcodesReadRateFirst: The read-rate-first barcode decoding template. It can read as many barcodes as possible.
* readSingleBarcode: This is a template designed for single barcode decoding. Only read one barcode at once.
