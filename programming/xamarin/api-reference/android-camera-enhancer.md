---
layout: default-layout
title: DCVCameraEnhancer Class under namespace Xamarin.Droid
description: DCVCameraEnhancer class of Xamarin.Droid implements the IDCVCameraEnhancer interface on Android.
keywords: DCVCameraEnhancer, API Reference, Xamarin, Xamarin Forms, Xamarin.Droid
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Xamarin.Droid - DCVCameraEnhancer
---

# DCVCameraEnhancer - DCVXamarin.Droid

`DCVCameraEnhancer` class of DCVXamarin.Droid implements interface `IDCVCameraEnhancer` on Android.

```c#
namespace DCVXamarin.Droid
{
    public class DCVCameraEnhancer : Object, IDCVCameraEnhancer
    {
        public DCVCameraEnhancer(Activity context);

        public Region ScanRegion { get; set; }
        public bool ScanRegionVisible { get；set; }

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
DCVCameraEnhancer dce = new DCVCameraEnhancer(context: this);
DCVBarcodeReader dbr = new DCVBarcodeReader();
LoadApplication(new App(dce, dbr));
```
