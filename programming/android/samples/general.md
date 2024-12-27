---
layout: default-layout
title: General Settings Sample - Dynamsoft Barcode Reader for Android
description: This is the General Settings Sample page of Dynamsoft Barcode Reader for Android SDK.
keywords: Android, samples, General
needAutoGenerateSidebar: true
breadcrumbText: GeneralSettings
permalink: /programming/android/samples/general.html
ignore: true
---

# GeneralSettings Sample

**View the sample code**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.2002/android/GeneralSettings" target="_blank">Android (Java) General Settings Sample</a>

This sample shows general barcode decoding settings and how to configure the settings when using Dynamsoft Barcode Reader Android SDK. You can see the following settings in the sample:

- [GeneralSettings Sample](#generalsettings-sample)
  - [Scan Mode](#scan-mode)
  - [Barcode Formats \& Expected Barcode Count](#barcode-formats--expected-barcode-count)
  - [Inverted Barcode Decoding](#inverted-barcode-decoding)
  - [Minimum Image Capture Interval](#minimum-image-capture-interval)
  - [Minimum Result Confidence](#minimum-result-confidence)
  - [Barcode Text RegEx Pattern](#barcode-text-regex-pattern)
  - [Result Deduplication](#result-deduplication)
  - [Result Cross Verification](#result-cross-verification)
  - [Scan Region](#scan-region)
  - [Highlight Decoded Barcodes](#highlight-decoded-barcodes)
  - [Vibration \& Beep](#vibration--beep)
  - [Torch Control](#torch-control)

## Scan Mode

- Continuous Scan: Decode the barcodes from the video streaming continuously.
- One-off Scan: Stop scanning when a barcode is decoded from the video streaming.

The video barcode decoding of Dynamsoft Barcode Reader is designed to be continuous, which means once you triggered method `startCapturing`, the video barcode decoding will not stop until you call method `stopCapturing`. The **One-off Scan** mode of **GeneralSettings sample** is configured by triggering `stopCapturing` when the barcode results are returned by `onDecodedBarcodesReceived`.

## Barcode Formats & Expected Barcode Count

The barcode formats settings and the barcode count settings are the most basic settings that determine the readability of your scan app.

**Barcode Format**

- You can view the enumeration [`BarcodeFormat`]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=java) for all the supported barcode formats.
- You can view <a href="https://www.dynamsoft.com/barcode-reader/barcode-types/" target="_blank">this page</a> for the introductions of barcode formats.

**Expected Barcode Count**

Through this parameter, you can tell how many barcodes you want to decode from a single image in one scan. If the `expectedBarcodesCount` is not reached, the library will continue try its best to decode the barcodes with other image processing modes or barcode decoding modes.

How to set `expectedBarcodesCount`:

- If you know exactly how may barcodes exist on the image, set it to that value.
- If you don't know exactly how may barcodes exist on the image and **speed** is at the first priority, set it to 0.
- If you don't know exactly how may barcodes exist on the image and **read-rate** is at the first priority, set it to the maximum possible value like 999.

```java
try {
   // mRouter is an instance of 'CaptureVisionRouter' class
   SimplifiedCaptureVisionSettings settings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   settings.barcodeSettings.barcodeFormatIds = EnumBarcodeFormat.BF_CODE_128 | EnumBarcodeFormat.BF_QR_CODE;
   settings.barcodeSettings.expectedBarcodesCount = 5;
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, settings);
} catch (CaptureVisionRouterException e) {
   e.printStackTrace();
}
```

## Inverted Barcode Decoding

If you are working with inverted barcodes, `GrayscaleTransformationModes` is the parameter to deal with them.

<div align="center">
    <p><img src="../../assets/inverted-barcode.png" width="20%" alt="invert"></p>
    <p>Inverted Barcode</p>
</div>

The candidate modes are:

- `GTM_ORIGINAL`: Decode original colour barcode.
- `GTM_INVERTED`: Decode inverted barcode.

The following code snippet shows how to configure `GrayscaleTransformationModes` via the `SimplifiedCaptureVisionSettings`.

```java
try {
   // mRouter is an instance of 'CaptureVisionRouter' class
   SimplifiedCaptureVisionSettings settings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   settings.barcodeSettings.grayscaleTransformationModes = new int[]{EnumGrayscaleTransformationMode.GTM_ORIGINAL,EnumGrayscaleTransformationMode.GTM_INVERTED};
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, settings);
} catch (CaptureVisionRouterException e) {
   e.printStackTrace();
}
```

The array `[EnumGrayscaleTransformationMode.GTM_ORIGINAL, EnumGrayscaleTransformationMode.GTM_INVERTED]` means:

In the first round of processing, the library will try to decode barcodes with original colour mode, which is specified in the first priority of the parameter array. If the count of decoded barcode doesn't reach the number of `expectedBarcodeCount`, the library will start another round of processing. The second round the library will focus on recognizing the inverted barcodes, which is specified in the second priority of the parameter array.

## Minimum Image Capture Interval

Property `minImageCaptureInterval` is an optional setting of video streaming barcode decoding when the scan mode is **continuous scan**. Generally, Dynamsoft Barcode Reader is able to process 15 to 30 frames per second when the video streaming resolution is 1080P. For some scenarios, you might use the continuous scan mode but don't need the performance to be that high. This feature can help you to reduce the battery consumption.

```java
try {
   // mRouter is an instance of 'CaptureVisionRouter' class
   SimplifiedCaptureVisionSettings settings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   settings.minImageCaptureInterval = 500;
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, settings);
} catch (CaptureVisionRouterException e) {
   e.printStackTrace();
}
```

## Minimum Result Confidence

Each barcode result has a `confidence`. It indicates the confidence level for a barcode result to be correct. Dynamsoft Barcode Reader algorithm is designed to separate the highly reliable results and unreliable results by confidence 30, which is set as the default value of `minResultConfidence`. You can either increase the `minResultConfidence` to get even more accuracy results or decrease the `minResultConfidence` to try decoding the badly printed barcodes.

```java
try {
   // mRouter is an instance of 'CaptureVisionRouter' class
   SimplifiedCaptureVisionSettings settings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   settings.barcodeSettings.minResultConfidence = 50;
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, settings);
} catch (CaptureVisionRouterException e) {
   e.printStackTrace();
}
```

## Barcode Text RegEx Pattern

Property `barcodeTextRegExPattern` is used during the barcode recognition process to obtain barcodes whose text matches a specific regular expression. Any barcodes that do not match this pattern will be ignored during the recognition process.

```java
try {
   // mRouter is an instance of 'CaptureVisionRouter' class
   SimplifiedCaptureVisionSettings settings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   settings.barcodeSettings.barcodeTextRegExPattern = "^[0-9]{10}$";
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, settings);
} catch (CaptureVisionRouterException e) {
   e.printStackTrace();
}
```

## Result Deduplication

Result deduplication is an optional setting of video streaming barcode decoding when the scan mode is **continuous scan**. As we mentioned above, Dynamsoft Barcode Reader can process the video streaming at a very high speed. When scanning a single item, the library returns multiple results with the same value when the barcode appears under the camera. For example, when scanning shopping items in a supermarket, you need only one result for each scan. The `ResultDeduplication` and `DuplicateForgetTime` features enable the device to output only one result even if the same barcode is scanned more than once in a short period.

> Note: You have to include `DynamsoftUtility` library to use the **Result Deduplication** feature.

```java
MultiFrameResultCrossFilter resultCrossFilter = new MultiFrameResultCrossFilter();
resultCrossFilter.enableResultDeduplication(EnumCapturedResultItemType.CRIT_BARCODE, true);
resultCrossFilter.setDuplicateForgetTime(EnumCapturedResultItemType.CRIT_BARCODE, 500);
// mRouter is an instance of 'CaptureVisionRouter' class
mRouter.addResultFilter(resultCrossFilter);
```

## Result Cross Verification

Enable `ResultCrossVerification` feature to improve the accuracy at the expense of a bit speed.

> Note: You have to include `DynamsoftUtility` library to use the **Result Cross Verification** feature.

```java
MultiFrameResultCrossFilter resultCrossFilter = new MultiFrameResultCrossFilter();
resultCrossFilter.enableResultCrossVerification(EnumCapturedResultItemType.CRIT_BARCODE, true);
// mRouter is an instance of 'CaptureVisionRouter' class
mRouter.addResultFilter(resultCrossFilter);
```

## Scan Region

For video barcode decoding scenarios, specifying a **scanRegion** can reduce the size of the processing area, which sharply increases the barcode decoding speed. To specify the scan region, you can use the **CameraEnhancer** method <a href="https://www.dynamsoft.com/camera-enhancer/docs/mobile/programming/android/primary-api/camera-enhancer.html#setscanregion" target="_blank">`setScanRegion`</a>. When the **scanRegion** is configured via **CameraEnhancer**, the video frames will be cropped based on the **scanRegion** before being processed by the barcode reader.

> Note: You have to include `DynamsoftCameraEnhancer` library to use the **Scan Region** feature. You must set `CameraEnhancer` as the input source when triggering the `setInput` method.

```java
CameraEnhancer mCameraEnhancer;
CameraView cameraView = findViewById(R.id.cameraView);
mCameraEnhancer = new CameraEnhancer(cameraView, MainActivity.this);
// Create a region object.
DSRect region = new DSRect();
region.top = 0.7;
region.bottom = 0.7;
region.left = 0.15;
region.right = 0.85;
// ture, measure by percentage; false, measure by pixel. 
region.measuredInPercentage = true;
try {
// Set scan region with the region object.
   mCameraEnhancer.setScanRegion(region);
} catch (CameraEnhancerException e) {
   e.printStackTrace();
}
```

**See also**

- [`setScanRegion`]({{ site.dce_android_api }}primary-api/camera-enhancer.html#setscanregion)

## Highlight Decoded Barcodes

Display a highlighted overlay on the location that a barcode is decoded.

> Note: You have to include `DynamsoftCameraEnhancer` library to use the **Highlight Decoded Barcodes** feature. You must set `CameraEnhancer` as the input source when triggering the `setInput` method.

```java
CameraEnhancer mCameraEnhancer;
DCECameraView cameraView = findViewById(R.id.cameraView);
mCameraEnhancer = new CameraEnhancer(cameraView, MainActivity.this);
cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID).setVisible(true);
```

**See also**

- [`CameraView`]({{ site.dce_android_api }}auxiliary-api/dcecameraview.html)
- [`DrawingLayer`]({{ site.dce_android_api }}auxiliary-api/dcedrawinglayer.html)

## Vibration & Beep

Trigger a beep or vibration. If you call them in the `onDecodedBarcodesReceived`, the device will trigger beep and vibration each time when a barcode is decoded.

> Note: You have to include `DynamsoftCameraEnhancer` library to use the **Vibration & Beep** feature.

```java
// mRouter is an instance of 'CaptureVisionRouter' class
mRouter.addResultReceiver(new CapturedResultReceiver() {
   @Override
   public void onDecodedBarcodesReceived(DecodedBarcodesResult result) {
         if (result != null && result.getItems() != null && result.getItems().length > 0) {
            Feedback.vibrate(MainActivity.this);
            Feedback.beep(MainActivity.this);
         }
   }
});
```

**See also**

- [`CameraView`]({{ site.dce_android_api }}auxiliary-api/dcefeedback.html)

## Torch Control

You can turn on the torch when processing the barcode in a dark environment. There are 3 ways for you to turn on the torch:

- Trigger `turnOnTorch` method.
- Add a `torchButton` on the view. Click the button to turn On the torch.
- Enable **smart torch** feature. When the environment light is dark, a torch button will appear on the camera view. You can click the button to turn on the torch.

> Note: You have to include `DynamsoftCameraEnhancer` library to use the **Vibration & Beep** feature.

Code snippet for triggering the `turnOnTorch` method:

```java
CameraEnhancer mCameraEnhancer;
CameraView cameraView = findViewById(R.id.cameraView);
mCameraEnhancer = new CameraEnhancer(cameraView, MainActivity.this);
mCameraEnhancer.turnOnTorch();
```

Code snippet for adding a `torchButton`:

```java
CameraEnhancer mCameraEnhancer;
CameraView cameraView = findViewById(R.id.cameraView);
mCameraEnhancer = new CameraEnhancer(cameraView, MainActivity.this);
// Set the torch button.
cameraView.setTorchButton(new Point(100,100),50,50,null,null);
```

Enable **smart torch**. If you have configured a `torchButton`, the `torchButton` you configured will become a **smart torch**.

```java
CameraEnhancer mCameraEnhancer;
DCECameraView cameraView = findViewById(R.id.cameraView);
mCameraEnhancer = new CameraEnhancer(cameraView, MainActivity.this);
// Enable smart torch feature.
try {
   mCameraEnhancer.enableEnhancedFeatures(EnumEnhancerFeatures.EF_SMART_TORCH);
} catch (CameraEnhancerException e) {
   e.printStackTrace();
}
```

**See also**

- [`turnOnTorch`]({{ site.dce_android_api }}primary-api/camera-enhancer.html#turnontorch)
- [`turnOffTorch`]({{ site.dce_android_api }}primary-api/camera-enhancer.html#turnofftorch)
- [`setTorchButton`]({{ site.dce_android_api }}auxiliary-api/dcecameraview.html#settorchbutton)
- [`enableEnhancedFeatures`]({{ site.dce_android_api }}primary-api/camera-enhancer.html#enableenhancedfeatures)
- [`EnumEnhancedFeatures`]({{ site.dcvb_enumerations }}enhanced-features.html?lang=android)
