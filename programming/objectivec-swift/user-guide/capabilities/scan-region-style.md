---
layout: default-layout
title: Scan Region Style - Dynamsoft Barcode Reader iOS
description: Learn how to configure the scan region style for Dynamsoft Barcode Reader iOS.
keywords: scan region, style, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Configure the Scan Region Style

## Visibility

After you call `setScanRegion`, the scan region is visible by default. You can hide it by calling `setScanRegionMaskVisible`.

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
[self.cameraView setScanRegionMaskVisible:false];
```
2. 
```swift
let region = Rect()
region.left = 0.15
region.top = 0.25
region.right = 0.85
region.bottom = 0.65
try? dce.setScanRegion(region)
cameraView.setScanRegionMaskVisible(false)
```

## Scan Region Mask Style

The scan region mask style includes the stroke color, stroke width, and mask color.

<div align="center">
    <p><img src="../../../assets/scan-region-style.png" width="70%" alt="barcode-scanner"></p>
    <p>Barcode Scanner UI Components</p>
</div>

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[self.cameraView setScanRegionMaskStyle:UIColor.whiteColor fillColor:[[UIColor darkGrayColor] colorWithAlphaComponent:0.35] strokeWidth:2];
```
2. 
```swift
cameraView.setScanRegionMaskStyle(.white, fillColor: UIColor.darkGray.withAlphaComponent(0.35), strokeWidth: 2)
```

## Laser

The scan laser is a light bar that moves up and down to indicate active scanning. It does not affect performance. It is hidden by default. When a scan region is set, the laser movement is limited to that region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[self.cameraView setScanLaserVisible:true];
```
2. 
```swift
cameraView.setScanLaserVisible(true)
```
