---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader for MAUI
description: This is the user guide of Dynamsoft Barcode Reader MAUI SDK.
keywords: user guide, maui
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---


# MAUI User Guide for Barcode Reader Integration

## Table of Contents

- [MAUI User Guide for Barcode Reader Integration](#maui-user-guide-for-barcode-reader-integration)
  - [Table of Contents](#table-of-contents)
  - [System Requirements](#system-requirements)
    - [.Net](#net)
    - [Android](#android)
    - [iOS](#ios)
  - [Installation](#installation)
    - [Visual Studio for Mac](#visual-studio-for-mac)
    - [Visual Studio for Windows](#visual-studio-for-windows)
  - [Build Your Barcode Scanner App](#build-your-barcode-scanner-app)
    - [Set up Development Environment](#set-up-development-environment)
    - [Initialize the Project](#initialize-the-project)
      - [Visual Studio](#visual-studio)
      - [Visual Studio for Mac](#visual-studio-for-mac-1)
    - [Include the Library](#include-the-library)
    - [Initialize MauiProgram](#initialize-mauiprogram)
    - [License Activation](#license-activation)
    - [Initialize the Capture Vision SDK](#initialize-the-capture-vision-sdk)
    - [Add the CameraView in the Main Page](#add-the-cameraview-in-the-main-page)
    - [Open the Camera and Start Barcode Decoding](#open-the-camera-and-start-barcode-decoding)
    - [Obtaining Barcode Results](#obtaining-barcode-results)
    - [Run the Project](#run-the-project)
  - [Customizing the Barcode Reader](#customizing-the-barcode-reader)
    - [Switching Preset Templates](#switching-preset-templates)
    - [Configuring the SimplifiedBarcodeReaderSettings](#configuring-the-simplifiedbarcodereadersettings)
    - [Customizing the Scan Region](#customizing-the-scan-region)
  - [Licensing](#licensing)

## System Requirements

### .Net

- .NET 7.0, 8.0 and 9.0.

### Android

- Supported OS: **Android 5.0** (API Level 21) or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Visual Studio 2022 recommended.
- JDK: 1.8+

### iOS

- Supported OS: **iOS 11.0** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Visual Studio 2022 for Mac and Xcode 14.3+ recommended.

## Installation

### Visual Studio for Mac

In the **NuGet Package Manager>Manage Packages for Solution** of your project, search for **Dynamsoft.CaptureVisionBundle.Maui**. Select Version **2.6.1000** and click **install**.

### Visual Studio for Windows

You need to add the library via the project file and complete additional steps for the installation.

1. Add the library in the project file:

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
        ...
        <ItemGroup>
            ...
            <PackageReference Include="Dynamsoft.CaptureVisionBundle.Maui" Version="2.6.1000" />
        </ItemGroup>
    </Project>
    ```

2. Open the **Package Manager Console** and run the following commands:

    ```bash
    dotnet build
    ```

> Note:
>
> - Windows system have a limitation of 260 characters in the path. If you don't use console to install the package, you will receive error "Could not find a part of the path 'C:\Users\admin\.nuget\packages\dynamsoft.imageprocessing.ios\2.4.300\lib\net7.0-ios16.1\Dynamsoft.ImageProcessing.iOS.resources\DynamsoftImageProcessing.xcframework\ios-arm64\dSYMs\DynamsoftImageProcessing.framework.dSYM\Contents\Resources\DWARF\DynamsoftImageProcessing'"
> - The library only support Android & iOS platform. Be sure that you remove the other platforms like Windows, maccatalyst, etc.

## Build Your Barcode Scanner App

Now you will learn how to create a simple barcode scanner using Dynamsoft Barcode Reader MAUI SDK.

### Set up Development Environment

If you are a beginner with MAUI, please follow the guide on the <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation" target="_blank">.Net MAUI official website</a> to set up the development environment.

### Initialize the Project

#### Visual Studio

1. Open the Visual Studio and select **Create a new project**.
2. Select **.Net MAUI App** and click **Next**.
3. Name the project **SimpleBarcodeScanner**. Select a location for the project and click **Next**.
4. Select **.Net 7.0** and click **Create**.

#### Visual Studio for Mac

1. Open Visual Studio and select **New**.
2. Select **Multiplatform > App > .Net MAUI App > C#** and click **Continue**.
3. Select **.Net 7.0** and click **Continue**.
4. Name the project **SimpleBarcodeScanner** and select a location, click **Create**.

### Include the Library

View the [installation section](#installation) on how to add the library.

### Initialize MauiProgram

In **MauiProgram.cs**, add a custom handler for the [`CameraView`]({{ site.dce_maui_api }}camera-view.html) control. Specifically, it maps the [`CameraView`]({{ site.dce_maui_api }}camera-view.html) type to the `CameraViewHandler` type.

```c#
using Microsoft.Extensions.Logging;
using Dynamsoft.CameraEnhancer.Maui;
using Dynamsoft.CameraEnhancer.Maui.Handlers;

namespace SimpleBarcodeScanner;

public static class MauiProgram
{
    public static MauiApp CreateMauiApp()
    {
        var builder = MauiApp.CreateBuilder();
        builder
            .UseMauiApp<App>()
            .ConfigureFonts(fonts =>
            {
                fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
                fonts.AddFont("OpenSans-Semibold.ttf", "OpenSansSemibold");
            })
            .ConfigureMauiHandlers(handlers =>
            {
                handlers.AddHandler(typeof(CameraView), typeof(CameraViewHandler));
            });

#if DEBUG
        builder.Logging.AddDebug();
#endif

        return builder.Build();
    }
}
```

### License Activation

The Dynamsoft Barcode Reader SDK needs a valid license to work. Please refer to the [Licensing](#licensing) section for more info on how to obtain a license.

Go to **MainPage.xaml.cs**. Add the following code to activate the license:

```c#
using Dynamsoft.License.Maui;
using System.Diagnostics;

namespace SimpleBarcodeScanner;

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

### Initialize the Capture Vision SDK

In the **MainPage.xaml.cs**, add the following code to initialize the Capture Vision SDK:

```c#
......
using Dynamsoft.CaptureVisionRouter.Maui;
using Dynamsoft.CameraEnhancer.Maui;
using Dynamsoft.Core.Maui;
using Dynamsoft.Utility.Maui;

public partial class MainPage : ContentPage, ILicenseVerificationListener, ICapturedResultReceiver
{
    CameraEnhancer enhancer;
    CaptureVisionRouter router;

    public MainPage()
    {
        ......

        // Create an instance of CameraEnhancer
        enhancer = new CameraEnhancer();
        // Create an instance of CaptureVisionRouter
        router = new CaptureVisionRouter();
        // Bind the router with the created CameraEnhancer
        router.SetInput(enhancer);
        // Add the result receiver to receive the decoded barcodes 
        router.AddResultReceiver(this);
    }
}
```

### Add the CameraView in the Main Page

In the **MainPage.xaml**, add the [`CameraView`]({{ site.dce_maui_api }}camera-view.html) and `Label` controls:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:controls="clr-namespace:Dynamsoft.CameraEnhancer.Maui;assembly=Dynamsoft.CaptureVisionRouter.Maui"
             x:Class="SimpleBarcodeScanner.MainPage"
             Title="MainPage">
    <AbsoluteLayout>
        <controls:CameraView x:Name="cameraView"
                             AbsoluteLayout.LayoutBounds="0,0,1,1"
                             AbsoluteLayout.LayoutFlags="All"/>
        <Label x:Name="label" Text = ''
                   AbsoluteLayout.LayoutBounds="0.5,0.1,300,25"
                   AbsoluteLayout.LayoutFlags="PositionProportional"/>
    </AbsoluteLayout>
</ContentPage>
```

### Open the Camera and Start Barcode Decoding

In this section, we are going to add code to start barcode decoding in the **MainPage.xaml.cs**.

```c#
......

public partial class MainPage : ContentPage, ILicenseVerificationListener, ICapturedResultReceiver, ICompletionListener
{
    ......

    protected override void OnHandlerChanged()
    {
        base.OnHandlerChanged();

        if (this.Handler != null)
        {
            enhancer.SetCameraView(cameraView);
        }

        base.OnHandlerChanged();
    }

    protected override async void OnAppearing()
    {
        base.OnAppearing();
        // Request camera permission
        await Permissions.RequestAsync<Permissions.Camera>();
        // Open camera
        enhancer?.Open();
        // Start barcode decoding
        router?.StartCapturing(EnumPresetTemplate.PT_READ_BARCODES, this);
    }

    protected override void OnDisappearing()
    {
        base.OnDisappearing();
        // Close camera
        enhancer?.Close();
        // Stop barcode decoding
        router?.StopCapturing();
    }

    public void OnSuccess()
    {
        Debug.WriteLine("Success");
    }

    public void OnFailure(int errorCode, string errorMessage)
    {
        Debug.WriteLine(errorMessage);
    }
}
```

Open the **Info.plist** file under the **Platforms/iOS/** folder (Open with XML Text Editor). Add the following lines to request camera permission on iOS platform:

```xml
<key>NSCameraUsageDescription</key>
<string>The sample needs to access your camera.</string>
```

### Obtaining Barcode Results

In **MainPage.xaml.cs**, implement [`ICapturedResultReceiver`]({{ site.dbr_maui_api }}capture-vision-router-lite/captured-result-receiver.html) to receive decoded barcodes result in  [`OnDecodedBarcodesReceived`]({{ site.dbr_maui_api }}capture-vision-router-lite/captured-result-receiver.html#ondecodedbarcodesreceived) callback function.

```c#
using Dynamsoft.BarcodeReader.Maui;
......

public partial class MainPage : ContentPage, ILicenseVerificationListener, ICapturedResultReceiver, ICompletionListener
{
    ......
    public void OnDecodedBarcodesReceived(DecodedBarcodesResult result)
    {
        if (result != null && result.Items != null && result.Items.Count > 0)
        {
            MainThread.BeginInvokeOnMainThread(() => { 
                label.Text = result.Items[0].Text;
            });
        }
    }
}
```

### Run the Project

Select your device and run the project.

> Note: If you are running Android only on Visual Studio Windows, please manually exclude iOS and Windows platforms. Otherwise, the Visual Studio will report type or namespace not found errors.

![Exclude iOS and Windows from targets](../assets/maui-exclude.png)

## Customizing the Barcode Reader

### Switching Preset Templates

Dynamsoft Barcode Reader SDK offers several preset templates for different popular scenarios. For the full set of templates, please refer to [`EnumPresetTemplate`]({{ site.dbr_maui_api }}capture-vision-router-lite/preset-template.html). Here is a quick example of prioritizing read rate for decoding:

```c#
router.StartCapturing(EnumPresetTemplate.PT_READ_BARCODES_READ_RATE_FIRST, this);
```

### Configuring the SimplifiedBarcodeReaderSettings

The SDK also supports a more granular control over the individual runtime settings rather than using a preset template. The main settings that you can control via this interface are which barcode formats to read, the expected number of barcodes to be read in a single image or frame, and the timeout, etc. For more info on each, please refer to [`SimplifiedBarcodeReaderSettings`]({{ site.dbr_maui_api }}simplified-barcode-reader-settings.html). Here is a quick example:

```c#
var cvSettings = router.GetSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
cvSettings.BarcodeSettings.BarcodeFormatIds = EnumBarcodeFormat.BF_EAN_13;
router.UpdateSettings(EnumPresetTemplate.PT_READ_BARCODES, cvSettings);
```

### Customizing the Scan Region

You can also limit the scan region of the SDK so that it doesn't exhaust resources trying to read from the entire image or frame.

```c#
var region = new DMRect(0.4f, 0.35f, 0.65f, 0.6f, true);
enhancer.SetScanRegion(region);
```

## Licensing

- A one-day trial license is available by default for every new device to try Dynamsoft Barcode Reader SDK.
- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&package=mobile&utm_source=docs){:target="_blank"} link.
- [Contact us](https://www.dynamsoft.com/company/contact/){:target="_blank"} to purchase a full license.
