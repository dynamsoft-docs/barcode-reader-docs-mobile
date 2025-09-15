---
layout: default-layout
title: DCVCameraEnhancer Class under namespace Xamarin.iOS
description: DCVCameraEnhancer class of Xamarin.iOS implements the IDCVCameraEnhancer interface on iOS.
keywords: DCVCameraEnhancer, API Reference, Xamarin, Xamarin Forms, Xamarin.iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Xamarin.iOS - DCVCameraEnhancer
---

# DCVCameraEnhancer - DCVXamarin.iOS

`DCVCameraEnhancer` class of DCVXamarin.iOS implements interface `IDCVCameraEnhancer` on iOS.

```c#
namespace DCVXamarin.iOS
{
    public class DCVCameraEnhancer : IDCVCameraEnhancer
    {
        public DCVCameraEnhancer();

        public Region ScanRegion { get; set; }
        public bool ScanRegionVisible { get; set; }

        public void Close();
        public Region GetScanRegion();
        public void Open();
        public void SetScanRegion(Region region);
        public void TurnOffTorch();
        public void TurnOnTorch();
    }
}
```

**Code Snippet**

```c#
DCVCameraEnhancer dce = new DCVCameraEnhancer();
DCVBarcodeReader dbr = new DCVBarcodeReader();
LoadApplication(new App(dce, dbr));
```
