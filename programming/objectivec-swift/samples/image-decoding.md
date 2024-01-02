---
layout: default-layout
title: DecodeFromAnImage Sample - Dynamsoft Barcode Reader for iOS
description: This is the page of DecodeFromAnImage sample of Dynamsoft Barcode Reader for iOS SDK.
keywords: android, samples, decode from an image
needAutoGenerateSidebar: true
breadcrumbText: DecodeFromAnImage
permalink: /programming/objectivec-swift/samples/image-decoding.html
---

# Decode From an Image Sample

`DecodeFromAnImage` sample shows how to pick an image from system album and decode the image.

**View the sample code**

* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/HelloWorld/DecodeFromAnImage/" target="_blank">Swift DecodeFromAnImage Sample</a>
* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/HelloWorld/DecodeFromAnImageObjc/" target="_blank">Objective-C DecodeFromAnImage Sample</a>

In the sample, you can see how to read an image from the album as a `UIImage` and use [`captureFromImage`]({{ site.dcv_ios_api }}capture-vision-router/single-file-processing.html#capturefromimage) method to process the UIImage.

The following `capture` methods are also available to process the other image types.

* [`captureFromFile`]({{ site.dcv_ios_api }}capture-vision-router/single-file-processing.html#capturefromfile): Process an image file with a file path.
* [`captureFromFileBytes`]({{ site.dcv_ios_api }}capture-vision-router/single-file-processing.html#capturefromfilebytes): Process an image file in memory.
* [`captureFromBuffer`]({{ site.dcv_ios_api }}capture-vision-router/single-file-processing.html#capturefrombuffer): Process a [`DSImageData`]({{ site.dcv_ios_api }}core/basic-structures/image-data.html)

When triggering the `capture` methods, a template name is required. You can use the enumeration `PresetTemplate` to specify one of the preset templates or input the name of your customized template. Barcode decoding preset templates are available as follow:

* readBarcodes: The default barcode decoding template. It is speed-first and only read one barcode from an single image.
* readBarcodesSpeedFirst: The speed-first barcode decoding template. Different from the default template, this template can read multiple barcodes at once.
* readBarcodesReadRateFirst: The read-rate-first barcode decoding template. It can read as many barcodes as possible.
* readSingleBarcode: This is a template designed for single barcode decoding. Only read one barcode at once.
