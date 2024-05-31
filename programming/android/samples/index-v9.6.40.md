---
layout: default-layout
title: Demos & Samples - Dynamsoft Barcode Reader for Android
description: This is the Demos & Samples page of Dynamsoft Barcode Reader for Android SDK.
keywords: Android, samples
needAutoGenerateSidebar: true
breadcrumbText: Samples
permalink: /programming/android/samples/index-v9.6.40.html
---

# Demo and Samples

## Demo

- <a href="https://download2.dynamsoft.com/dbr/android/DynamsoftBarcodeReaderDemoAndroid-9.4.0.apk" target="_blank">Download Barcode Scanner X.</a>

## Samples

**Native Android Samples**

| Sample Name | Description | Tags |
| ----------- | ----------- | ---- |
| [HelloWorld](helloworld.md) | The simplest video streaming barcode scanner. The scan mode is one-off scanning. | One-off scan / Barcode format |
| [GeneralSettings](general.md) | Displays general barcode decoding settings and camera settings like barcode formats, exepcted barcode count and scan region settings. The default scan mode is continuous scanning. | Continuous scan / Barcode format |
| [PerformanceSettings](performance.md) | Parameter configuration guide on improving the speed, read-rate and accuracy of barcode reading. The sample includes the code of image decoding from the ablem. | Continuous scan / Image decoding / Speed / Read rate / Accuracy |
| [ReadADriversLicense](drivers-license.md) | Introduce how to read the PDF417 barcode on a US driver's license and extract the driver's information. | PDF417 / US drivers' license / One-off scan |
| [DecodeWithCameraX](no-camera-enhancer.md) | Almost the same with the Helloworld sample but using **CameraX** as the source of the video streaming. | Continuous scan / CameraX |
| [TinyBarcodeDecoding](tiny-barcode.md) | The sample to tell you how to process the tiny barcodes. Including zoom and focus control. | Tiny barcode / Zoom / Focus |
| [ImageDecoding](image-decoding.md) | The sample shows how to pick an image from the album for barcode decoding. | Image Decoding |

**Cross-platform Samples**

| Sample Name | Description |
| ----------- | ----------- |
| <a href="https://github.com/Dynamsoft/capture-vision-react-native-samples" target="_blank">BarcodeReaderSimpleSample (React Native)</a> | Run a simple video streaming barcode scanner on React Native platform. |
| <a href="https://github.com/Dynamsoft/capture-vision-flutter-samples" target="_blank">BarcodeReaderSimpleSample (Flutter)</a> | Run a simple video streaming barcode scanner on Flutter platform. |
| <a href="https://github.com/Dynamsoft/capture-vision-xamarin-forms-samples" target="_blank">BarcodeReaderSimpleSample (Xamarin.Forms)</a> | Run a simple video streaming barcode scanner on Xamarin.Forms platform. |
| <a href="https://github.com/Dynamsoft/capture-vision-cordova-samples" target="_blank">BarcodeReaderSimpleSample (Cordova)</a> | Run a simple video streaming barcode scanner on Cordova platform. |

## About Dynamsoft Barcode Reader Android Samples

Before you start viewing the samples, the following concepts may help you understand how to get started with Dynamsoft Barcode Reader.

### License

You need a valid license to unlock the full feature of **Dynamsoft Barcode Reader**. Otherwise, the barcode results will be encoded and the coordinates of barcode location results are offset.

- The samples on GitHub are provided with time-limited free trial, which require network connection to work.
- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs&package=android){:target="_blank"} link. Offline trial license is also available by [contacting us](https://www.dynamsoft.com/contact/){:target="_blank"}.
- If you download the sample along with the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?product=dbr&utm_source=guide&package=android" target="_blank">Installation Package</a>, the 30-day trial license is already included in the sample code.

### Scan Mode

Here we define 3 different scan modes:

- **One-off scanning**: Scan barcode(s) from the video streaming and stop scanning after barcode results are output.
- **Continuous scanning**: Scan barcode(s) from the video streaming and output barcode results continuously.
- **Image decoding**: Read barcode(s) from an image, an image in the memory or a bitmap by triggering [image decoding method(s)](../api-reference/primary-decode.md).

For the majority of our samples, one-off scanning and continuous scanning from the video streaming are using **Dynamsoft Camera Enhancer** (DCE) to capture the video streaming. For the features and APIs of DCE please view <a href="https://www.dynamsoft.com/camera-enhancer/docs/mobile/programming/android/" target="_blank">DCE online documents</a>. You can also use a third party library like CameraX to capture the video streaming.

### Performance

In the samples, we demonstrate the performance settings from 3 different aspects: **Speed**, **Read Rate** and **Accuracy**. The parameter configurations are generally speed-friendly, read-rate-friendly and accuracy-friendly settings but might not be the best settings for your usage scenario. The performance sample can help you get a basic understanding of the Dynamsoft Barcode Reader parameters. Please feel free to <a href="https://www.dynamsoft.com/contact/" target="_blank">contact us</a> for further support on optimizing the parameters.
