---
layout: default-layout
title: Read from a Specific Area - Dynamsoft Barcode Reader Android
description: Learn how to read from a specific area using the Dynamsoft Barcode Reader Android SDK.
keywords: user guide, read specific area, Android, java, kotlin
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Read from a Specific Area

## Set a Scan Region on Camera

### Work with Foundational APIs

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
CameraView cameraView = findViewById(R.id.camera_view);
CameraEnhancer mCamera = new CameraEnhancer(cameraView, this);
try {
   mCamera.setScanRegion(new DSRect(0.15f, 0.25f, 0.85f, 0.65f, true));
} catch (CameraEnhancerException e) {
   throw new RuntimeException(e);
}
```
2. 
```kotlin
val cameraView = findViewById<CameraView>(R.id.camera_view)
val mCamera = CameraEnhancer(this)
mCamera.scanRegion = DSRect(0.15f, 0.25f, 0.85f, 0.65f, true)
```

**Related APIs**

- [`CameraEnhancer`]({{ site.dbr_android_api }}camera-enhancer/camera-enhancer.html)
  - [`setScanRegion`]({{ site.dbr_android_api }}camera-enhancer/camera-enhancer.html#setscanregion)

### Work with BarcodeScanner APIs

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
// Margin left 15%, margin top 30%, margin right 85%, margin bottom 70%
config.setScanRegion(new DSRect(0.15f, 0.25f, 0.85f, 0.65f, true));
```
2. 
```kotlin
val config = BarcodeScannerConfig().apply {
   // Margin left 15%, margin top 30%, margin right 85%, margin bottom 70%
   scanRegion = DSRect(0.15f, 0.3f, 0.85f, 0.7f, true)
}
```

**Related APIs**

- [`BarcodeScannerConfig`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html)
   - [`setScanRegion`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setscanregion)

## Set an ROI via Simplified Settings

> [!Important]
> Simplified Settings are only available for the **Foundational APIs**.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
CaptureVisionRouter mRouter = new CaptureVisionRouter();
try {
   SimplifiedCaptureVisionSettings captureVisionSettings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   Quadrilateral roiQuad = new Quadrilateral();
   roiQuad.points[0] = new Point(15,30);
   roiQuad.points[1] = new Point(85,30);
   roiQuad.points[2] = new Point(85,70);
   roiQuad.points[3] = new Point(15,70);
   captureVisionSettings.roi = roiQuad;
   captureVisionSettings.roiMeasuredInPercentage = true;
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, captureVisionSettings);
} catch (CaptureVisionRouterException e) {
   e.printStackTrace();
}
```
2. 
```kotlin
val mRouter: CaptureVisionRouter? = CaptureVisionRouter()
try {
   val captureVisionSettings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES)
   val roiQuad = Quadrilateral()
   roiQuad.points[0] = Point(15, 30)
   roiQuad.points[1] = Point(85, 30)
   roiQuad.points[2] = Point(85, 70)
   roiQuad.points[3] = Point(15, 70)
   captureVisionSettings.roi = roiQuad
   captureVisionSettings.roiMeasuredInPercentage = true
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, captureVisionSettings)
} catch (e: CaptureVisionRouterException) {
   e.printStackTrace()
}
```

## Set ROIs in Customized Template

Define a single ROI:

```json
{
   "CaptureVisionTemplates": [
      {
            "Name" : "CV_0",
            "ImageROIProcessingNameArray": ["barcode-decoding-roi-1" ]
      }       
   ],
   "TargetROIDefOptions" : [
      {
         "Name" : "barcode-decoding-roi-1",
         "TaskSettingNameArray": ["barcode-decoding-task-1"],
         "Location": 
         {
            "Offset": {
               "MeasuredByPercentage" : 1,
               "FirstPoint" : [ 15, 30 ],
               "SecondPoint" : [ 85, 30 ],
               "ThirdPoint" : [ 85, 70 ],
               "FourthPoint" : [ 15, 70 ],
            }
         }
      }
   ]
}
```

You can define multiple ROIs in `TargetROIDefOptions`. For each ROI, you can assign a different task or reuse the same task.

```json
{
   "CaptureVisionTemplates": [
      {
            "Name" : "CV_0",
            "ImageROIProcessingNameArray": ["barcode-decoding-roi-1","barcode-decoding-roi-2" ]
      }       
   ],
   "TargetROIDefOptions" : [
      {
         "Name" : "barcode-decoding-roi-1",
         "TaskSettingNameArray": ["barcode-decoding-task-1"],
         "Location": 
         {
            "Offset": {
               "MeasuredByPercentage" : 1,
               "FirstPoint" : [ 15, 20 ],
               "SecondPoint" : [ 85, 40 ],
               "ThirdPoint" : [ 85, 40 ],
               "FourthPoint" : [ 15, 20 ]
            }
         }
      },{
         "Name" : "barcode-decoding-roi-2",
         "TaskSettingNameArray": ["barcode-decoding-task-1"],
         "Location": 
         {
            "Offset": {
               "MeasuredByPercentage" : 1,
               "FirstPoint" : [ 15, 60 ],
               "SecondPoint" : [ 85, 80 ],
               "ThirdPoint" : [ 85, 80 ],
               "FourthPoint" : [ 15, 60 ]
            }
         }
      }
   ]
}
```
