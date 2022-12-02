---
layout: default-layout
title: Dynamsoft Barcode Reader for Android - General Settings Sample
description: This is the General Settings Sample page of Dynamsoft Barcode Reader for Android SDK.
keywords: Android, samples, General
needAutoGenerateSidebar: true
breadcrumbText: GeneralSettings
permalink: /programming/objectivec-java/samples/general.html
---

# GeneralSettings Sample

This sample shows general barcode decoding settings and how to configure the settings when using Dynamsoft Barcode Reader Android SDK. You can see the following settings in the sample:

- [Scan Mode](#scan-mode)
- [Barcode Format & Expected Barcode Count](#barcode-formats--expected-barcode-count)
- [Inverted Barcode Decoding](#inverted-barcode-decoding)
- [Minimum Decode Interval](#minimum-decode-interval)
- [Duplicate Filter](#duplicate-filter)
- [Minimum Result Confidence](#minimum-result-confidence)
- [Result Verification](#result-verification)
- [Scan Region](#scan-region)
- [Display of Overlay](#display-of-overlay)
- [Vibration & Beep](#vibration--beep)
- [Torch Control](#torch-control)

**View the Sample(s)**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/GeneralSettingsObjC/" target="_blank">Objective-C General Settings Sample</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Swift/GeneralSettingsSwift/" target="_blank">Swift General Settings Sample</a>

## Scan Mode

- Continuous Scan: Decode the barcodes from the video streaming continuously. You can add
- One-off Scan: Stop scanning when a barcode is decoded from the video streaming.

The video barcode decoding of Dynamsoft Barcode Reader is designed to be continuous, which means once you triggered method `startScanning`, the video barcode decoding will not stop until you call method `stopScanning`. The **One-off Scan** mode of **GeneralSettings sample** is configured by triggering `stopScanning` when the barcode results are returned by `textResultCallback`.

## Barcode Formats & Expected Barcode Count

The barcode formats settings and the barcode count settings are the most basic settings that determine the readability of your scan app. These parameters are all available for users to make changes through the class [`PublicRuntimeSettings`]({{ site.oc_api }}auxiliary-iPublicRuntimeSettings.html). To view all available barcode formats, please view the enumeration [`BarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,java) and [`BarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,java).

## Inverted Barcode Decoding

If you are working with inverted barcodes, `GrayscaleTransformationModes` is the parameter to deal with them.

<div align="center">
    <p><img src="../../assets/inverted-barcode.png" width="20%" alt="invert"></p>
    <p>Inverted Barcode</p>
</div>

The candidate modes are:

- `GTM_ORIGINAL`: Decode original coloured barcode.
- `GTM_INVERTED`: Decode inverted barcode.

There are 2 ways for you to configure the algorithm parameters. You can either upload the parameter from `PublicRuntimeSettings` or include it in the JSON template.

### Update PublicRuntimeSettings

The following code snippet shows how to configure `GrayscaleTransformationModes` via the `PublicRuntimeSettings`.

```java
try {
   PublicRuntimeSettings settings = mReader.getRuntimeSettings();
   settings.furtherModes.grayscaleTransformationModes = new int[]{EnumGrayscaleTransformationMode.GTM_ORIGINAL,EnumGrayscaleTransformationMode.GTM_INVERTED};
   mReader.updateRuntimeSettings(settings);
} catch (BarcodeReaderException e) {
   e.printStackTrace();
}
```

The array `[EnumGrayscaleTransformationMode.original, EnumGrayscaleTransformationMode.inverted]` means:

In the first round of processing, the library will try to decode barcodes with original colour mode, which is specified in the first priority of the parameter array. If the count of decoded barcode doesn't reach the number of `expectedBarcodeCount`, the library will start another round of processing. The second round the library will focus on recognizing the inverted barcodes, which is specified in the second priority of the parameter array.

### Upload JSON Template

To upload the GrayscaleTransformationModes settings via a JSON template, you have to include the following snippet in your JSON template:

```json
{
   "ImageParameter": {
      "Name": "ImageParameter1",
      ...
      // You have to include the following parts.
      "GrayscaleTransformationModes": [
         {
            "Mode": "GTM_ORIGINAL"
         },
         {
            "Mode": "GTM_INVERTED" 
         }
      ],
      ...
   }
}
```

You can read <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/structure-and-interfaces-of-parameters.html?ver=latest" target="_blank"> template structure</a> to learn more about how to configure the JSON template.

The follow code snippets shows how to upload the JSON template:

**Upload JSON template as a String**

```java
try {
   mReader.initRuntimeSettingsWithString("{\"ImageParameter\":{\"Name\":\"ImageParameter1\",\"GrayscaleTransformationModes\":[{\"Mode\":\"GTM_ORIGINAL\"},{\"Mode\":\"GTM_INVERTED\"}]}}",EnumConflictMode.CM_OVERWRITE);
} catch (BarcodeReaderException e) {
   e.printStackTrace();
}
```

**Upload JSON template as a File**

```java
try {
   mReader.initRuntimeSettingsWithFile("Your file path", EnumConflictMode.CM_OVERWRITE);
} catch (BarcodeReaderException e) {
   e.printStackTrace();
}
```

## Minimum Decode Interval

Property `minImageDecodingInterval` is an optional setting of video streaming barcode decoding when the scan mode is **continuous scan**. Generally, Dynamsoft Barcode Reader is able to process 15 to 30 frames per second when the video streaming resolution is 1080P. For some scenarios, you might use the continuous scan mode but don't need the performance to be that high. This feature can help you to reduce the battery consumption.

```java
mReader.setMinImageDecodingInterval(500);
```

## Duplicate Filter

Property `enableDuplicateFilter` and `duplicateForgetTime` are optional settings of video streaming barcode decoding when the scan mode is **continuous scan**. As we mentioned above, Dynamsoft Barcode Reader can process the video streaming at a very high speed. When scanning a single item, the library returns multiple results with the same value when the barcode appears under the camera. For example, when scanning shopping items in a supermarket, you need only one result for each scan. The `duplicateFilter` feature enable the device to output only one result even if the same barcode is scanned more than once in a short period. As a result you can count each item only once under the **continuous scan** mode by configuring the `duplicateFilter` and `duplicateForgetTime`.

```java
mReader.setDuplicateForgetTime(500);
mReader.enableDuplicateFilter(true);
```

## Minimum Result Confidence

Each barcode result has a `confidence`. It indicates the confidence level for a barcode result to be correct. Dynamsoft Barcode Reader algorithm is designed to separate the highly reliable results and unreliable results by confidence 30, which is set as the default value of `minResultConfidence`. You can either increase the `minResultConfidence` to get even more accuracy results or decrease the `minResultConfidence` to try decoding the badly printed barcodes. You can either set the `minResultConfidence` via `PublicRuntimeSettings` or include it in the JSON template.

```java
try {
   PublicRuntimeSettings settings = mReader.getRuntimeSettings();
   settings.minResultConfidence = 50;
   mReader.updateRuntimeSettings(settings);
} catch (BarcodeReaderException e) {
   e.printStackTrace();
}
```

## Result Verification

Enable `ResultVarification` feature to improve the accuracy at the expense of a bit speed. You can enable the result verification feature by configuring the property `enableResultVerification`.

```java
mReader.enableResultVerification(true);
```

## Scan Region

For video barcode decoding scenarios, specifying a **scanRegion** can reduce the size of the processing area, which sharply increases the barcode decoding speed. To specify the scan region, you can use the **CameraEnhancer** method <a href="https://www.dynamsoft.com/camera-enhancer/docs/programming/ios/primary-api/camera-enhancer.html?ver=latest#setscanregion" target="_blank">`setScanRegion`</a>. When the **scanRegion** is configured via **CameraEnhancer**, the video frames will be cropped based on the **scanRegion** before being processed by the barcode reader.

```java
CameraEnhancer mCameraEnhancer;
DCECameraView cameraView = findViewById(R.id.cameraView);
mCameraEnhancer = new CameraEnhancer(MainActivity.this);
mCameraEnhancer.setCameraView(cameraView);
// Create a region object.
RegionDefinition region = new RegionDefinition();
region.regionTop = 70;
region.regionBottom = 70;
region.regionLeft = 15;
region.regionRight = 85;
// 1, measure by percentage; 0, measure by pixel. 
region.regionMeasuredByPercentage = 1;
// Set scan region with the region object.
try {
   mCameraEnhancer.setScanRegion(region);
} catch (CameraEnhancerException e) {
   e.printStackTrace();
}
```

## Display of Overlay

Display a highlighted overlay on the location that a barcode is decoded.

> Note: This feature is only available when using video streaming barcode decoding and the video source must be set to `DynamsoftCameraEnhancer`.

```java
CameraEnhancer mCameraEnhancer;
DCECameraView cameraView = findViewById(R.id.cameraView);
mCameraEnhancer = new CameraEnhancer(MainActivity.this);
mCameraEnhancer.setCameraView(cameraView);
cameraView.setOverlayVisible(true);
```

## Vibration & Beep

Trigger a beep or vibration. If you call them in the `textResultCallback`, the device will trigger beep and vibration each time when a barcode is decoded.

```java
public void textResultCallback(int id, ImageData imageData, TextResult[] textResults) {
   DCEFeedback.vibrate(MainActivity.this);
   DCEFeedback.beep(MainActivity.this);
}
```

## Torch Control

You can turn on the torch when processing the barcode in a dark environment. There are 3 ways for you to turn on the torch:

- Trigger `turnOnTorch` method.
- Add a `torchButton` on the view. Click the button to turn On the torch.
- Enable **smart torch** feature. When the environment light is dark, a torch button will appear on the camera view. You can click the button to turn on the torch.

Code snippet for triggering the `turnOnTorch` method:

```java
CameraEnhancer mCameraEnhancer;
DCECameraView cameraView = findViewById(R.id.cameraView);
mCameraEnhancer = new CameraEnhancer(MainActivity.this);
mCameraEnhancer.setCameraView(cameraView);
mCameraEnhancer.turnOnTorch();
```

Code snippet for adding a `torchButton`:

```java
CameraEnhancer mCameraEnhancer;
DCECameraView cameraView = findViewById(R.id.cameraView);
mCameraEnhancer = new CameraEnhancer(MainActivity.this);
mCameraEnhancer.setCameraView(cameraView);
// Set the torch button.
cameraView.setTorchButton(new Point(100,100),50,50,null,null);
```

Enable **smart torch**. If you have configured a `torchButton`, the `torchButton` you configured will become a **smart torch**.

```java
CameraEnhancer mCameraEnhancer;
DCECameraView cameraView = findViewById(R.id.cameraView);
mCameraEnhancer = new CameraEnhancer(MainActivity.this);
mCameraEnhancer.setCameraView(cameraView);
// Enable smart torch feature.
try {
   mCameraEnhancer.enableFeatures(EnumEnhancerFeatures.EF_SMART_TORCH);
} catch (CameraEnhancerException e) {
   e.printStackTrace();
}
```
