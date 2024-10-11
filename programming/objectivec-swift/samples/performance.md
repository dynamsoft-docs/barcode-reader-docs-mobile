---
layout: default-layout
title: Performance Settings Sample - Dynamsoft Barcode Reader for iOS
description: This is the Performance Settings Sample page of Dynamsoft Barcode Reader for iOS SDK.
keywords: iOS, sample, Performance
needAutoGenerateSidebar: true
breadcrumbText: Performance Settings
permalink: /programming/objectivec-swift/samples/performance.html
ignore: true
---

# PerformanceSettings Sample

**View the sample**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/PerformanceSettings" target="_blank">iOS (Swift) Performance Settings Sample</a>

## Templates

| Template Name | Description |
| -------- | ----------- |
| `ReadBarcodes_Default` | The default template for DBR mobile editions. |
| `ReadSingleBarcode` | The video streaming barcode scanning template for single barcode usage scenario. |
| `ReadBarcodes_SpeedFirst` | The video streaming barcode scanning template for speed first usage scenario. |
| `ReadBarcodes_ReadRateFirst` | The video streaming barcode scanning template for read-rate first usage scenario. |

## Parameter Parsing

**ExpectedBarcodeCount**

Parameter [`ExpectedBarcodesCount`]({{site.dcv_parameters_reference}}barcode-reader-task-settings/expected-barcodes-count.html) is an int value that refers to how many barcodes you would like to decode from a single image or frame. The barcode reader will try to find as many barcodes as the [`ExpectedBarcodesCount`]({{site.dcv_parameters_reference}}barcode-reader-task-settings/expected-barcodes-count.html) number. Set the [`ExpectedBarcodesCount`]({{site.dcv_parameters_reference}}barcode-reader-task-settings/expected-barcodes-count.html) to 1 can maximize the processing speed of your program but limit the read rate at the same time.

**BarcodeFormatIds**

Parameter [`BarcodeFormatIds`]({{site.dcv_parameters_reference}}barcode-reader-task-settings/barcode-format-ids.html) is an int value that controls the recognizable barcode formats. The fewer formats you set, the higher speed your app will be.

**ScaleDownThreshold**

The image/frame will be continuously scaled down until it is smaller than the [`ScaleDownThreshold`]({{site.dcv_parameters_reference}}image-parameter/scale-down-threshold.html). You can use this parameter to improve the processing speed but the read rate and accuracy will decline on decoding the small-module barcode.

**Timeout**

The parameter [`Timeout`]({{site.dcv_parameters_reference}}capture-vision-template/timeout.html) controls the maximum time consumption on processing a single image/frame. For image decoding scenarios, you can set a longer [`Timeout`]({{site.dcv_parameters_reference}}capture-vision-template/timeout.html) to ensure the barcode reader decode as many barcodes as possible from the image. For video barcode decoding scenarios, not all video frame contains a barcode. You can reduce the [`Timeout`]({{site.dcv_parameters_reference}}capture-vision-template/timeout.html) to enable your barcode reader to quickly quit the video frames without a barcode. The Timeout parameter benefits the speed of barcode decoding but might reduce the read rate.

**DeblurModes**

The [`DeblurModes`]({{site.dcv_parameters_reference}}barcode-reader-task-settings/deblur-modes.html) parameter enables the barcode reader to try different algorithms on processing the blurry barcodes. This parameter will benefit the read rate but reduce the processing speed.

### Other Settings

**Set Scan Region**

Configuring the scan region via **CameraEnhancer** method [`setScanRegion`]({{ site.dce_ios }}primary-api/camera-enhancer.html#setscanregion) can further improve the barcode decoding speed. The video frames will be cropped based on the **scanRegion** setting before they are processed by the barcode reader. The **scanRegion** setting benefits the processing speed but might reduce the read rate at the same time.

<div align="center">
    <p><img src="../../assets/region-definition.png" width="70%" alt="region-def"></p>
    <p>Reduce the Size of Scan Area</p>
</div>

**Multi-Frame Verification**

When a barcode result has been decoded more than once within a short period of time, we can confirm it is a correct result and output it. However, if a barcode result has never been decoded a second time within a period of time, we consider it a misread result and discard it. You can enable the multi-frame verification to further improve the result accuracy via the method [`enableResultCrossVerification`]({{site.dcv_ios_api}}utility/multi-frame-result-cross-filter.html#enableresultcrossverification).

**Frame Filter**

Frame filter is one of the camera enhancer features. You can enable it via **CameraEnhancer** method [`enableEnhancedFeatures`]({{ site.dce_ios }}primary-api/camera-enhancer.html#enableenhancedfeatures). The frame filter helps in filtering blurry video frames to improve the barcode decoding accuracy. It also improves the speed performance of low-end devices.
