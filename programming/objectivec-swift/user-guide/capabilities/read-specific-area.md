---
layout: default-layout
title: Read from a Specific Area - Dynamsoft Barcode Reader iOS
description: Learn how to read from a specific area using the Dynamsoft Barcode Reader iOS SDK.
keywords: user guide, read specific area, iOS, objective-c, swift
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Read from a Specific Area

## Set a Scan Region on Camera

### Work with Foundational APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSRect *region = [[DSRect alloc] init];
region.left = 0.15;
region.top = 0.25;
region.right = 0.85;
region.bottom = 0.65;
[self.dce setScanRegion:region error:nil];
```
2. 
```swift
let region = Rect()
region.left = 0.15
region.top = 0.25
region.right = 0.85
region.bottom = 0.65
try? dce.setScanRegion(region)
```

**Related APIs**

- [`CameraEnhancer`]({{ site.dbr_ios_api }}camera-enhancer/camera-enhancer.html)
   - [`setScanRegion`]({{ site.dbr_ios_api }}camera-enhancer/camera-enhancer.html#setscanregion)

### Work with BarcodeScanner APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
// Margin left 15%, margin top 30%, margin right 85%, margin bottom 70%
DSRect *region = [[DSRect alloc] init];
region.left = 0.15;
region.top = 0.25;
region.right = 0.85;
region.bottom = 0.65;
config.scanRegion = region;
```
2. 
```swift
let config = BarcodeScannerConfig()
let region = Rect()
region.left = 0.15
region.top = 0.30
region.right = 0.85
region.bottom = 0.70
config.scanRegion = region
```

**Related APIs**

- [`BarcodeScannerConfig`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html)
   - [`setScanRegion`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#setscanregion)

## Set an ROI via Simplified Settings

> [!Important]
> Simplified Settings are only available for the **Foundational APIs**.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError *error = nil;
DSSimplifiedCaptureVisionSettings *captureVisionSettings = [self.cvr getSimplifiedSettings:DSPresetTemplateReadBarcodes error:&error];
DSQuadrilateral *roiQuad = [[DSQuadrilateral alloc] init];
roiQuad.points[0] = [[DSPoint alloc] initWithX:15 y:30];
roiQuad.points[1] = [[DSPoint alloc] initWithX:85 y:30];
roiQuad.points[2] = [[DSPoint alloc] initWithX:85 y:70];
roiQuad.points[3] = [[DSPoint alloc] initWithX:15 y:70];
captureVisionSettings.roi = roiQuad;
captureVisionSettings.roiMeasuredInPercentage = true;
[self.cvr updateSettings:DSPresetTemplateReadBarcodes settings:captureVisionSettings error:&error];
```
2. 
```swift
do {
   let captureVisionSettings = try cvr.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue)
   let roiQuad = Quadrilateral()
   roiQuad.points[0] = Point(15, 30)
   roiQuad.points[1] = Point(85, 30)
   roiQuad.points[2] = Point(85, 70)
   roiQuad.points[3] = Point(15, 70)
   captureVisionSettings.roi = roiQuad
   captureVisionSettings.roiMeasuredInPercentage = true
   try cvr.updateSettings(PresetTemplate.readBarcodes.rawValue, settings: captureVisionSettings)
} catch {
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
