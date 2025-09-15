---
layout: default-layout
title: Interface IBarcodeResultListener of Dynamsoft Capture Vision Xamarin Edition
description: The interface IBarcodeResultListener
keywords: Barcode Result Listener, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: IBarcodeResultListener
---

# IBarcodeResultListener

`IBarcodeResultListener` is the interface to handle callbacks when the barcode results are returned.

```c#
interface IBarcodeResultListener
```

| Method | Description |
| ------ | ----------- |
| [BarcodeResultCallback](#barcoderesultcallback) | The callback is triggered when the library finished processing and returns the barcode results. |

## BarcodeResultCallback

The callback is triggered when the library finished processing and returns the barcode results. Users can get barcode results from the method.

```c#
void BarcodeResultCallback(int frameID, BarcodeResult[] barcodeResults);
```

**Parameters**

`[in] barcodeResults`: A group of barcode results that are decoded from the latest processed video frame.

**Code Snippet**

```c#
// Add IBarcodeResultListener to your page class
public partial class DBRRendererPage : ContentPage, IBarcodeResultListener
{
    public DBRRendererPage()
    {
        // Add the result listener so that you can receive the barcode results from the BarcodeResultCallback.
        App.barcodeReader.AddResultListener(this);
        // You have to set camera enhancer as the video source to decode from video stream.
        App.barcodeReader.SetCameraEnhancer();
        ...
    }
    ...
    protected override void OnAppearing()
    {
        base.OnAppearing();
        // Open the camera.
        App.camera.Open();
        // Start the barcode decoding thread.
        App.barcodeReader.StartScanning();
    }

    protected override void OnDisappearing()
    {
        base.OnDisappearing();
        App.camera.Close();
        App.barcodeReader.StopScanning();
    }
    public void BarcodeResultCallback(BarcodeResult[] barcodeResults)
    {
        // Add your code to execute here when barcode results are received.
    }
}
```
