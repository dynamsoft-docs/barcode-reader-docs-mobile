---
layout: default-layout
title: Migrate from Xamarin Forms to MAUI - Dynamsoft Barcode Reader for MAUI
description: This is the migration guide from Xamarin Forms to MAUI
keywords: user guide, maui, xamarin forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# How to migrate from Xamarin Forms to MAUI

The Dynamsoft Barcode Reader SDK has been refactored to align with the [DynamsoftCaptureVision (DCV)]({{ site.dcvb_architecture }}) architecture. To upgrade to version 10.x, we recommend following the [User Guide](user-guide.md) and re-writing your code accordingly.

## Update the Project

Previously, you created a Mobile App (Xamarin.Forms) project. Now, you’ll need to create a standalone .NET MAUI App project.

## Update the Library

In your Xamarin.Forms project, you referenced the **Dynamsoft.CaptureVision.Xamarin.Forms** library. Now, in your MAUI project, you’ll need to reference the **Dynamsoft.BarcodeReaderBundle.Maui** library. Please refer to the [User Guide](user-guide.md#installation) for further instructions.

## Update the License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.initLicense` | `LicenseManager.initLicense` |

- code in Xamarin.Forms

```c#
public partial class App : Application, ILicenseVerificationListener
{
    public App(IDCVCameraEnhancer dce, IDCVBarcodeReader dbr)
    {
        ...
        // Initialize the license of barcode reader module. Please note that the following license is a public trial.
        barcodeReader.InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", this);
    }

    // Implement LicenseVerificationCallback to get message from the license server.
    public void LicenseVerificationCallback(bool isSuccess, string msg)
    {
        if (!isSuccess)
        {
            System.Console.WriteLine(msg);
        }
    }
}
```

- code in MAUI

```c#
public partial class MainPage : ContentPage, ILicenseVerificationListener
{
    public MainPage()
    {
        InitializeComponent();
        LicenseManager.InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", this);
    }
    public void OnLicenseVerified(bool isSuccess, string message)
    {
        if (!isSuccess)
        {
            Debug.WriteLine(message);
        }
    }
}
```

## Update Video Streaming Decoding APIs

The APIs for decoding video frames has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.SetCameraEnhancer` | `CaptureVisionRouter.SetInput` |
| `BarcodeReader.StartScanning` | `CaptureVisionRouter.StartCapturing` |
| `BarcodeReader.StopScanning` | `CaptureVisionRouter.StopCapturing` |
| `BarcodeReader.AddResultReceiver` | `CaptureVisionRouter.addResultReceiver` |
| `BarcodeReader.Set/GetMinImageReadingInterval` | `SimplifiedCaptureVisionSettings.MinImageCaptureInterval` |
| `BarcodeReader.EnableResultVerification` | `MultiFrameResultCrossFilter.EnableResultCrossVerification` |
| `BarcodeReader.EnableDuplicateFilter` | `MultiFrameResultCrossFilter.EnableResultDeduplication` |
| `interface IBarcodeResultListener` | `interface ICapturedResultReceiver` |
| `class BarcodeResult` | `class BarcodeResultItem` |

## Migrate Your Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please <a href="https://download2.dynamsoft.com/dcv/TemplateConverter.zip" target="_blank">download the TemplateConverter tool</a> or <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your template.

The template-based APIs have been updated as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.UpdateRuntimeSettings` | `CaptureVisionRouter.InitSettings` |
| `BarcodeReader.ResetRuntimeSettings` | `CaptureVisionRouter.ResetRuntimeSettings` |
| `BarcodeReader.OutputRuntimeSettingsToString` | `CaptureVisionRouter.OutputSettings` |

## Migrate Your DBRPublicRuntimeSettings

The class `DBRPublicRuntimeSettings` has been refactored. The APIs for accessing and updating `DBRPublicRuntimeSettings` has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.GetRuntimeSettings` | `CaptureVisionRouter.GetSimplifiedSettings` |
| `BarcodeReader.UpdateRuntimeSettings` | `CaptureVisionRouter.UpdateSettings` |

### Migrate to SimplifiedCaptureVisionSettings

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings`. They can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedCaptureVisionSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `Timeout` | [`Timeout`]({{ site.dcv_maui_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html?product=dbr) |

### Migrate to SimplifiedBarcodeReaderSettings

The following properties are replaced by similar properties under `SimplifiedBarcodeReaderSettings`. The majority of them can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `MinBarcodeTextLength` | [`MinBarcodeTextLength`]({{ site.dbr_maui_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html?product=dbr) |
| `MinResultConfidence` | [`MinResultConfidence`]({{ site.dbr_maui_api  }}simplified-barcode-reader-settings.html#minresultconfidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html?product=dbr) |
| `ExpectedBarcodesCount` | [`ExpectedBarcodesCount`]({{ site.dbr_maui_api  }}simplified-barcode-reader-settings.html#expectedbarcodescount) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html?product=dbr) |
| `BarcodeFormatIds` | [`BarcodeFormatIds`]({{ site.dbr_maui_api  }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html?product=dbr) |
| `BarcodeFormatIds_2` | [`BarcodeFormatIds`]({{ site.dbr_maui_api  }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html?product=dbr) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
