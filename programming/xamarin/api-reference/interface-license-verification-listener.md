---
layout: default-layout
title: ILicenseVerificationListener of Dynamsoft Capture Vision Xamarin Edition
description: The interface ILicenseVerificationListener
keywords: License verification, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: ILicenseVerificationListener
---

# ILicenseVerificationListener

`ILicenseVerificationListener` is the interface to handle callback when using `InitLicense`.

```c#
interface ILicenseVerificationListener
```

| Method | Description |
| ------ | ----------- |
| [LicenseVerificationCallback](#licenseverificationcallback) | The callback is triggered when the library finished processing and returns the barcode results. |

## LicenseVerificationCallback

The method handles license verification message that returned by the license server.

```c#
void LicenseVerificationCallback(bool isSuccessful, string errorMsg)
```

**Parameters**

`[in] isSuccessful`: Whether the license verification was successful.  
`[in] errorMsg`: The error message from license server.

**Code Snippet**

```c#
public partial class DBRRendererPage : ContentPage, ILicenseVerificationListener
{
    public DBRRendererPage()
    {
        App.barcodeReader.InitLicense("Put your license key here.", this);
        ...
    }
    ...
    public void ILicenseVerificationListener.LicenseVerificationCallback(bool isSuccess, string msg)
    {
        if (!isSuccess) 
        {
            Console.WriteLine(msg);
        }
    }
}
```
