---
layout: default-layout
title: DCVCameraView Class of Dynamsoft Capture Vision Xamarin Edition
description: This page is the API reference of DCVCameraView class
keywords: Camera view, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: DCVCameraView
---

# Class DCVCameraView

`DCVCameraView` is used to provide a UI for the camera display and any related UI elements. `DCVCameraView` extends the [`View` class](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.view?view=xamarin-forms) which is where the `HorizontalOptions` and `VerticalOptions` come from.

```c#
class DCVCameraView
```

| Property | Description |
| -------- | ----------- |
| [`OverlayVisible`](#overlayvisible) | A property that indicates whether the `overlays` are visible. |
| [`TorchButton`](#torchbutton) | A property that determines whether a torch button will be displayed on the `DCVCameraView` and how the torch button will be displayed. |

## OverlayVisible

A property that indicates whether the `overlays` are visible.

```c#
bool OverlayVisible;
```

**Code Snippet**

```xml
<local:DCVCameraView
    OverlayVisible="True"
    HorizontalOptions="FillAndExpand"
    VerticalOptions="FillAndExpand" >
```

## TorchButton

A property that determines whether a torch button will be displayed on the `DCVCameraView` and how the torch button will be displayed.

```c#
TorchButton Torchbutton;
```

**Code Snippet**

```xml
<local:DCVCameraView
    OverlayVisible="True"
    HorizontalOptions="FillAndExpand"
    VerticalOptions="FillAndExpand" >
    <local:DCVCameraView.TorchButton>
        <local:TorchButton
            TorchOnImage="abc.png"
            TorchOffImage="abc.png"
            Visible="True">
            <local:TorchButton.Location>
                <local:Rect Width="50" Height="50" X="300" Y="300"></local:Rect>
            </local:TorchButton.Location>
        </local:TorchButton>
    </local:DCVCameraView.TorchButton>
</local:DCVCameraView>
```
>Note: Learn how to [add an image in Xamarin.iOS](https://learn.microsoft.com/en-us/xamarin/ios/app-fundamentals/images-icons/displaying-an-image?tabs=macos) and [add an image in Xamarin.Android](../../../faq/xamarin-how-to-add-image.md)
