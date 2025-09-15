---
layout: default-layout
title: Interface IDCVCameraEnhancer of Dynamsoft Capture Vision Xamarin Edition
description: This page is the API reference of Interface IDCVCameraEnhancer
keywords: Interface IDCVCameraEnhancer, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: IDCVCameraEnhancer
---

# Interface IDCVCameraEnhancer

The interface `IDCVCameraEnhancer` provides camera and related hardware controlling APIs.

```c#
interface IDCVCameraEnhancer
```

<style>
  .markdown-body > table {
    display: table;
    width: 100%;
  }
  .markdown-body > table tr th:first-child {
    width: 30%;
  }
</style>

| Method | Description |
| ------- | ----------- |
| [`ScanRegion`](#scanregion) | The property for users to specify the region of interest. |
| [`ScanRegionVisible`](#scanregionvisible) | Set or get the visibility of the scan region. |
| [`Open`](#open) | Open the camera. |
| [`Close`](#close) | Close the camera. |
| [`TurnOnTorch`](#turnontorch) | Turn on the torch. |
| [`TurnOffTorch`](#turnofftorch) | Turn off the torch. |
| [`SetFocus`](#setfocus) | Trigger a focus at the targeting point and set the subsequent focus mode after focused. |
| [`EnableFeatures`](#enablefeatures) | Enable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) value. |
| [`DisableFeatures`](#disablefeatures) | Disable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) values. |
| [`IsFeatureEnabled`](#isfeatureenabled) | Returns a boolean value that means whether the feature(s) you input is (are) enabled. |
| [`SetZoomFactor`](#setzoomfactor) | Set the zoom factor. The camera will zoom in/out immediately after this method is triggered. |
| [`AutoZoomRange`](#autozoomrange) | A [`Range`](class-range.md) value that indicates the maximum available zoom factor of the device. |
| [`MaxZoomFactor`](#maxzoomfactor) | A float property that indicates the maximum available zoom factor of the device. |

## ScanRegion

Specify a region of interest. Once the **scan region** is set, the video frames will be cropped so that the library process the region only. The **scan region** you specified will be displayed on the view by default. You can hide the **scan region** by setting [`ScanRegionVisible`](#scanregionvisible) to **false**.

```c#
Region ScanRegion { get; set; }
```

**Parameters**

`scanRegion`: An object of [`Region`](class-region.md) class which indicates the location of the region.

**Related APIs**

- [ScanRegionVisible](#scanregionvisible): You can set whether to display the **scan region**.
- [BarcodeLocationResult](class-barcode-location-result.md): Since the video frame is cropped based on the **scan region**, the `Location` you get from `BarcodeLocationResult` is based on the cropped video frame.

**Code Snippet**

Specify a scan region and display it on the view:

```c#
DCVXamarin.Region scanRegion = new DCVXamarin.Region();
scanRegion.RegionTop = 30;
scanRegion.RegionBottom = 70;
scanRegion.RegionLeft = 15;
scanRegion.RegionRight = 85;
scanRegion.RegionMeasuredByPercentage = 1;
protected override void OnAppearing()
{
    base.OnAppearing();
    App.dbr.StartScanning();
    App.dce.Open();
    // Set scan region on appearing
    App.dce.ScanRegion = scanRegion;
}
```

**Related APIs**

- [Region](class-region.md)

## ScanRegionVisible

Set or get the visibility of the scan region.

```c#
bool ScanRegionVisible { get; set; }
```

**Code Snippet**

The following code snippet shows how to set the scan region but hide it on the view.

```c#
DCVXamarin.Region scanRegion = new DCVXamarin.Region();
scanRegion.RegionTop = 30;
scanRegion.RegionBottom = 70;
scanRegion.RegionLeft = 15;
scanRegion.RegionRight = 85;
scanRegion.RegionMeasuredByPercentage = 1;
protected override void OnAppearing()
{
    base.OnAppearing();
    App.dbr.StartScanning();
    App.dce.Open();
    App.dce.ScanRegion = scanRegion;

    // Hide the scan region with the following line.
    App.dce.ScanRegionVisible = false;
}
```

## Open

Open the camera.

```c#
void Open();
```

## Close

Close the camera.

```c#
void Close();
```

## TurnOnTorch

Turn on the torch.

```c#
void TurnOnTorch();
```

## TurnOffTorch

Turn off the torch.

```c#
void TurnOffTorch();
```

## SetFocus

Trigger a focus at the targeting point and set the subsequent focus mode after focused.

```c#
void SetFocus(Point focusPoint, EnumFocusMode subsequentFocusMode);
```

Parameters

`[in] focusPosition`: An Point object indicates the interest area.  
`[in] subsequentFocusMode`: Specify a mode with [`EnumFocusMode`](enum-focus-mode.md). If you set the focus mode to `FM_LOCKED`, the focallength will be lock after the focus. Otherwise, the continuous auto focus that control by the hardware is still enabled.

## EnableFeatures

Enable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) value.

```c#
void EnableFeatures(EnumEnhancerFeatures enhancerFeatures);
```

**Parameters**

`enhancerFeatures`: The combined value of [`EnumEnhancerFeatures`](enum-enhancer-features.md).

## DisableFeatures

Disable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) values.

```c#
void DisableFeatures(EnumEnhancerFeatures enhancerFeatures);
```

**Parameters**

`enhancerFeatures`: The combined value of [`EnumEnhancerFeatures`](enum-enhancer-features.md).

## isFeatureEnabled

Returns a boolean value that means whether the feature(s) you input is (are) enabled.

```c#
bool IsFeatureEnabled(EnumEnhancerFeatures enhancerFeatures);
```

**Parameters**

`enhancerFeatures`: The combined value of [`EnumEnhancerFeatures`](enum-enhancer-features.md).

## SetZoomFactor

Set the zoom factor. The camera will zoom in/out immediately after this method is triggered.

```c#
void SetZoomFactor(float factor);
```

**Parameters**

`factor`: The target zoom factor.

## AutoZoomRange

A [`Range`](class-range.md) value that indicates the maximum available zoom factor of the device.

```c#
Range AutoZoomRange { get; set; }
```

## MaxZoomFactor

A float property that indicates the maximum available zoom factor of the device.

```c#
float MaxZoomFactor { get; }
```
