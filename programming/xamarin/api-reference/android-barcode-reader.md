---
layout: default-layout
title: DCVBarcodeReader Class under namespace Xamarin.Droid
description: DCVBarcodeReader class of Xamarin.Droid implements the IDCVBarcodeReader interface on Android.
keywords: DCVBarcodeReader, API Reference, Xamarin, Xamarin Forms, Xamarin.Droid
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Xamarin.Droid - DCVBarcodeReader
---

# DCVBarcodeReader - DCVXamarin.Droid

`DCVBarcodeReader` class of DCVXamarin.Droid implements interface `IDCVBarcodeReader` on Android.

```c#
namespace DCVXamarin.Droid
{
    public class DCVBarcodeReader : Java.Lang.Object, IDCVBarcodeReader, ITextResultListener, IJavaObject, IDisposable, IJavaPeerable, IDBRLicenseVerificationListener
    {
        public DCVBarcodeReader();

        public void AddResultListener(IBarcodeResultListener listener);
        public void DBRLicenseVerificationCallback(bool p0, Java.Lang.Exception p1);
        public DBRRuntimeSettings GetRuntimeSettings();
        public string GetVersion();
        public void InitLicense(string license, ILicenseVerificationListener listener);
        public string OutputRuntimeSettingsToString();
        public void ResetRuntimeSettings();
        public void SetCameraEnhancer(IDCVCameraEnhancer dce);
        public void StartScanning();
        public void StopScanning();
        public void TextResultCallback(int i, ImageData p1, TextResult[] results);
        public void UpdateRuntimeSettings(DBRRuntimeSettings settings);
        public void UpdateRuntimeSettings(EnumDBRPresetTemplate presetTemplate);
        public void UpdateRuntimeSettings(string jsonTemplate);
        public int MinImageReadingInterval { get; set; }
        public bool EnableResultVerification { get; set; }
        public bool EnableDuplicateFilter { get; set; }
        public int DuplicateForgetTime { get; set; }
    }
}
```

**Code Snippet**

```c#
DCVCameraEnhancer dce = new DCVCameraEnhancer(context: this);
DCVBarcodeReader dbr = new DCVBarcodeReader();
LoadApplication(new App(dce, dbr));
```
