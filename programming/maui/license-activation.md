---
layout: default-layout
title: License Activation - Dynamsoft Barcode Reader MAUI Edition
description: Initialize the license of Dynamsoft Barcode Reader MAUI edition.
keywords: license initialization, licensing
needAutoGenerateSidebar: true
---

# License Initialization

## Get a trial license

You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs&package=mobile){:target="_blank"} link.

You can contact our support team via the [Contacting Us](https://www.dynamsoft.com/contact/){:target="_blank"} link when your license generation failed.

## Get a Full License

[Contact us](https://www.dynamsoft.com/company/contact){:target="_blank"} to purchase a full license.

## Set the License In the Code

### For BarcodeScanner

```csharp
var config = new BarcodeScannerConfig("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
var result = await BarcodeScanner.Start(config);
```

### For Foundational Barcode Reader

The following shows how to set the license in the code.

```csharp
public partial class CameraPage : ContentPage, ILicenseVerificationListener
{
    public CameraPage()
    {
        InitializeComponent();
        LicenseManager.InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", this);
    }
    public void OnLicenseVerified(bool isSuccess, string message)
    {
        if (!isSuccess)
        {
            Console.WriteLine("License initialization failed: " + message);
        }
    }
    public void OnFailure(int errorCode, string errorMessage)
    {
        MainThread.BeginInvokeOnMainThread(() =>
        {
            DisplayAlert("Error", errorMessage, "OK");
        });
    }
}
```
